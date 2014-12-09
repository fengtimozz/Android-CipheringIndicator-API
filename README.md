#### ANDROID PROJECT TO CREATE AN API FOR [ANDROID ISSUE #5353](https://code.google.com/p/android/issues/detail?id=5353)

![Ciphering](http://fs1.d-h.st/view/L6I/00153/ciphering.png)

* **PRE-ALPHA** - SEEKING KICKSTARTER FUNDING AND DEVELOPERS
* KICKSTARTER: [Android Privacy Indicator - Identify Cell Network Tampering](https://www.kickstarter.com/projects/1760935672/android-cipher-indicator-identify-cell-network-tam)
* ANDROID ISSUE: https://code.google.com/p/android/issues/detail?id=5353

---

#### PROJECT SUMMARY

Cell phone calls are typically encrypted as they travel through the air. In some cases though they may not be. An increasing number of rogue cell phone towers have been identified in the USA and beyond. These towers can be made for under $1,000 even by non-techies. The parts and instructions are readily available online. Essentially almost anyone with a little bit of motivation and money can eavesdrop on your calls. For Android phones there is a great project called the [Android IMSI-Catcher Detector](https://secupwn.github.io/Android-IMSI-Catcher-Detector/) which is working hard to detect and avoid fake base stations and also wants to use our API we are creating here. Feel free to install their App and contribute pull requests for development.

But yet Android itself lacks an API to indicate that you may have connected to a rogue tower or that voice encryption has been disabled. [Android Issue #5353](https://code.google.com/p/android/issues/detail?id=5353) has been open and is known to Google since 2009. It was created in an attempt to notify Google of the lack of an indicator notifying you if encryption is currently enabled and if so what encryption algorithm is being used. Even though the [GSM 02.07 specification (Version 7.1.0 Release 1998)](http://www.3gpp.org/ftp/Specs/archive/02_series/02.07/0207-710.zip) lists the Ciphering Indicator as a required part of the GSM, it has been ignored until Nick from the Android Security Team [responded](https://code.google.com/p/android/issues/detail?id=5353#c12).

The "Ciphering Indication Feature" is not only missing in Android, but is also often suppressed by the network provider by setting the OFM (Operational Feature Monitor) bit in the "administrative data" field (EFAD, see GSM 11.11, 10.3.18) on the SIM card, in order to make IMEI/IMSI catchers (GSM interceptors) invisible for the phone user. Usually the Ciphering Indicator is turned off and you cannot modify the administrative data in the SIM. Our API shall detect whenever the Ciphering is turned off for whatever reason.

---

#### CIPHERING INDICATOR DETAILS

[Quote](https://code.google.com/p/android/issues/detail?id=5353#c19) from one of Nicks Android Security colleagues:

>All GSM crypto is broken. Furthermore, the same keys are used for A5/1, A5/2, A5/3, and GPRS, i.e. it is sufficient to get the phone to use one of the weakers ciphers and break that. Most phones are happy to use A5/2 if the base station requests it, and it can be trivially broken in less than a second with no precomputations or memory required, ie a man-in-the-middle attack can be used to get the keys which can then be used to decipher any communication made with any stronger ciphers (it's a bit more complicated, but only a bit, see http://cryptome.org/gsm-crack-bbk.pdf for the full story. Section 5 describes the attack on "any cipher").

---

* A5/0: No ciphering at all
* [A5/1](https://en.wikipedia.org/wiki/A5/1): Strong(er) ciphering, intended for use in North America and Europe
* [A5/2](https://en.wikipedia.org/wiki/A5/2): Weak ciphering, intended for use in other parts of the world, now deprecated
* [A5/3](https://en.wikipedia.org/wiki/A5/3): Even "stronger" ciphering with open design

---

* :warning: [Operation Auroragold: How the NSA Hacks Cellphone Networks Worldwide](https://firstlook.org/theintercept/2014/12/04/nsa-auroragold-hack-cellphones/)
* :warning: Known attacks on A5/3 (KASUMI): "[OPULENT PUP](https://firstlook.org/theintercept/document/2014/12/04/opulent-pup-encryption-attack/)" and "[WOLFRAMITE](https://firstlook.org/theintercept/document/2014/12/04/wolframite-encryption-attack)")

---

```
B.1.26	Ciphering Indicator

The ciphering indicator feature allows the ME to detect that ciphering is 
not switched on and to indicate this to the user, as defined in GSM 02.09.

The ciphering indicator feature may be disabled by the home network 
operator setting data in the "administrative data" field (EFAD) in the 
SIM, as defined in GSM 11.11.

If this feature is not disabled by the SIM, then whenever a connection is 
in place, which is, or becomes unenciphered, an indication shall be given 
to the user.

Ciphering itself is unaffected by this feature, and the user can choose 
how to proceed.
```

Think of it like the green lock icon you see when you visit your banks website. To finally make this missing Ciphering Indicator come to life on Android, this repository is meant to craft the API and let it be added to AOSP when finished. This will essentially improve Android for everyone.

So please don't be afraid to contribute - it's worth the effort!

![CipheringNotPrivided](https://upload.wikimedia.org/wikipedia/commons/thumb/e/ee/CipheringNotProvided.jpg/200px-CipheringNotProvided.jpg) ![UnencryptedConnection](http://fs1.d-h.st/view/2ifR/00153/unencrypted.png) ![Ciphering Unavailable](http://i50.fastpic.ru/big/2012/1207/bc/79126b9dfabba04aff00d3409165bebc.png)

---

#### REQUIREMENTS PER GOOGLE

From: Nick 11/19/2014

>Ideally, I'm hoping for someone who can identify the areas where Android needs to change, put together a small proposal / writeup with sufficient technical information that I can have it reviewed by our telecom engineers here, and then do the implementation of the changes.

>All of our code is in the Android open source project, so a lot of documents, like how to build Android, are already available. I believe it's a simple matter of plumbing the cipher mode from the underlying code to an application accessible API, but I could be wrong.

>So far, there's really no other information about this feature, other than what's in the bug. I would suggest using the bug to collect the information.

---

#### DEVELOPMENT ROADMAP

Note: This Development Roadmap is by far not complete and will be edited.

1. Get more details on how to properly start off the very raw base API
2. Create the very raw base API for scraping relevant CI veriables
3. Expand the Android Ciphering Indicator API and polish it up for Google
4. Create a pull request for adding the final API to Android Open Source
