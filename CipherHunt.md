## CURRENT STATUS

Still unclear where low level network information can be pulled.  Some debate as to whether it can somehow be pulled from RIL / Telephony or whether it needs to come from the BP (Baseband Processor). This page reflects our hard hunt.

---

## WHERE?

#### [Chin-Hung](mailto:chh@google.com) - RIL

* [android/platform/hardware/ril/master](https://android.googlesource.com/platform/hardware/ril/+/master)

>I found android.telephony and android.telephony.gsm packages and some vendor >specific cipher modules, but I am really not familiar with these 	>modules. Nick should be able to give better suggestions.

#### [Kayash](mkayyash@google.com) - Telephony

* [android/platform/.../internal/ telephony/gsm/GSMPhone.java](https://android.googlesource.com/platform/frameworks/opt/telephony/+/83a97603d6e38ca5600cc12780fbfbee0cfe483f/src/java/com/android/internal/telephony/gsm/GSMPhone.java#106)

>Thanks Matas, I'm more of a kernel guy, so I forwarded this message to our Android Telephony Team who can help you better.

#### [Andrew](anwlee@google.com)  - Telephony

* [android/platform/packages/services/Telephony/master](https://android.googlesource.com/platform/packages/services/Telephony/+/master)

>Willing to help. Wanted to talk to Nick, fowarded nick email.

####  [Baligh](baligh@google.com)

* [android/platform/packages/services/Telecomm/master](https://android.googlesource.com/platform/packages/services/Telecomm/+/master)

>Hello Sir, I am sorry I am unable to help on this issue. Please contact Nick directly. Thanks.

---

## THEORIES

Here are some theories we've collected. If you have one too (or know the truth) let us know!

>I doubt cipher is even in Google's closed-source Android, unless someone knows of public, "vanilla" releases that expose this information. We could reverse-engineer it. Some manufacturers put it in their own builds (MTK and Samsung? I think you guys have said so), which we might RE into a general solution for the underlying basebands.

-joey

>You need to find a way to get this info from BP to AP

-andre

>...requires baseband support

-thegrugq

---

## Resources:

* [Radio Layer Interface | Android Open Source](http://www.kandroid.org/online-pdk/guide/telephony.html)
* [Using SIM card as secure element in Android](http://nelenkov.blogspot.com/2013/09/using-sim-card-as-secure-element.html)
* Qualcomm baseband team? Note: They will likely not respond.
* JOAO: [Low Level Network Information](https://groups.google.com/forum/#!topic/android-platform/tVyNMnXtcEI)
* [E:V:A](https://github.com/E3V3A): [SEEK for Android](https://groups.google.com/forum/#!topic/seek-for-android/OALRa9EBxMI)
