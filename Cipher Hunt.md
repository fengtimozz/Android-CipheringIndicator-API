##CURRENT STATUS
Still unclear where low level network information can be pulled.  Some debate as to whether it can somehow be pulled from RIL / Telephony or whether it needs to come from the BP (Baseband Processor).

##WHERE?

####Chin-Hung - RIL
#####https://android.googlesource.com/platform/hardware/ril/+/master chh@google.com

>"I found android.telephony and android.telephony.gsm packages and some vendor >specific cipher modules, but I am really not familiar with these 	>modules. Nick should be able to give better suggestions."

####Kayash - Telephony
#####https://android.googlesource.com/platform/frameworks/opt/telephony/+/83a97603d6e38ca5600cc12780fbfbee0cfe483f/src/java/com/android/internal/telephony/gsm/GSMPhone.java#106 - mkayyash@google.com

>Thanks Matas, I'm more of a kernel guy, so I forwarded this message to our Android Telephony Team who can help you better.

#### Andrew  - Telephony
#####https://android.googlesource.com/platform/packages/services/Telephony/+/master  - anwlee@google.com

Willing to help. Wanted to talk to Nick, fowarded nick email.

####  Baligh
#####https://android.googlesource.com/platform/packages/services/Telecomm/+/master - baligh@google.com

>Hello Sir
I am sorry I am unable to help on this issue.  please contact Nick directly.
thanks

##THEORIES
>I doubt cipher is even in Google's closed-source Android, unless someone knows of public, "vanilla" releases that expose this information.  We could reverse-engineer it.  Some manufacturers put it in their own builds (MTK and Samsung? I think you guys have said so), which we might RE into a general solution for the underlying basebands.
joey


>you need to find a way to get this info from BP to AP
andre


>...requires baseband support
thegrugq

#Resources:
http://www.kandroid.org/online-pdk/guide/telephony.html

http://nelenkov.blogspot.com/2013/09/using-sim-card-as-secure-element.html

Qualcomm baseband team?

JOAO:  LOW LEVEL NETWORK INFORMATION
https://groups.google.com/forum/#!topic/android-platform/tVyNMnXtcEI

EVA: SEEK for ANDROID
https://groups.google.com/forum/#!topic/seek-for-android/OALRa9EBxMI


