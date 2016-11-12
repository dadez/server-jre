# server-jre
oracle server-jre based on alpine linux 3.4 official

#build
docker build -t server-jre .

#build passing java version as argument
docker build --build-arg JAVA_UPDATE_VERSION=112 --build-arg JAVA_BUILD_NUMBER=15 -t server-jre .

#run
docker run -it --rm jre8-alpine:u111 java -version
java version "1.8.0_111"
Java(TM) SE Runtime Environment (build 1.8.0_111-b14)
Java HotSpot(TM) 64-Bit Server VM (build 25.111-b14, mixed mode)
 
 
#the default truststore is empty (at least one entry is needed by opensaml framework)
## ? How to use $JAVA_HOME instead of full path
docker run -it --rm server-jre keytool -list -keystore /opt/java/server-jre1.8.0_111/jre/lib/security/cacerts -protected
 