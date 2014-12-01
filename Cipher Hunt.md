##WHERE?
#####https://android.googlesource.com/platform/hardware/ril/+/master chh@google.com

>I found android.telephony and android.telephony.gsm packages and some vendor >specific cipher modules, but I am really not familiar with these 	>modules. Nick should be able to give better suggestions.


#####https://android.googlesource.com/platform/frameworks/opt/telephony/+/83a97603d6e38ca5600cc12780fbfbee0cfe483f/src/java/com/android/internal/telephony/gsm/GSMPhone.java#106 - mkayyash@google.com


#####https://android.googlesource.com/platform/packages/services/Telephony/+/master  - anwlee@google.com

#####https://android.googlesource.com/platform/packages/services/Telecomm/+/master - baligh@google.com

##THEORIES
>I doubt cipher is even in Google's closed-source Android, unless someone >knows of public, "vanilla" releases that expose this information.  We could >reverse-engineer it.  Some manufacturers put it in their own builds (MTK and >Samsung? I think you guys have said so), which we might RE into a general >solution for the underlying basebands.
joey

>you need to find a way to get this info from BP to AP
andre

>"...requires baseband support"
thegrugq

#Resources:
http://www.kandroid.org/online-pdk/guide/telephony.html
http://nelenkov.blogspot.com/2013/09/using-sim-card-as-secure-element.html
Qualcomm baseband team?