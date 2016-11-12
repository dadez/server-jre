# server-jre
oracle server-jre

#build
docker build -t jre8-alpine .

#run
docker run -it --rm jre8-alpine:u111 java -version
java version "1.8.0_111"
Java(TM) SE Runtime Environment (build 1.8.0_111-b14)
Java HotSpot(TM) 64-Bit Server VM (build 25.111-b14, mixed mode)
 
 
#the default keystore is empty (at least one entry is needed by opensaml framework)
docker run -it --rm jre8-alpine:u111 keytool -list -keystore /opt/java/server-jre1.8.0_111/jre/lib/security/cacerts -protected
 
*****************  WARNING WARNING WARNING  *****************
* The integrity of the information stored in your keystore  *
* has NOT been verified!  In order to verify its integrity, *
* you must provide your keystore password.                  *
*****************  WARNING WARNING WARNING  *****************
 
Keystore type: JKS
Keystore provider: SUN
 
Your keystore contains 1 entry
 
swissgovernmentrootcaii, Oct 26, 2016, trustedCertEntry,
Certificate fingerprint (SHA1): C7:F7:CB:E2:02:36:66:F9:86:02:5D:4A:3E:31:3F:29:EB:0C:5B:38
