# Description
oracle server-jre based on alpine linux 3.4 official

the default truststore is empty (at least one entry is needed by opensaml framework)

#build
* build simple
```
docker build -t server-jre .
```

* build passing java version as argument
```
docker build --build-arg JAVA_UPDATE_VERSION=112 \
--build-arg JAVA_BUILD_NUMBER=15 \
-t server-jre .
```
* autobuild on docker hub
dadez/jre:latest

#run
* check java version
```
docker run -it --rm server-jre java -version

java version "1.8.0_111"
Java(TM) SE Runtime Environment (build 1.8.0_111-b14)
Java HotSpot(TM) 64-Bit Server VM (build 25.111-b14, mixed mode)
```

* list truststore
```
docker run -it --rm server-jre keytool -list \
-keystore /opt/java/server-jre1.8.0_111/jre/lib/security/cacerts \
-protected
```
