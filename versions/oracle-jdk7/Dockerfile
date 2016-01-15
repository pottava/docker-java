# Oracle JDK v1.7.0_80
# docker run --rm pottava/java:7 java -version
# docker run --rm pottava/java:7 env

FROM alpine:3.3

ENV JAVA_VERSION_MAJOR=7 \
    JAVA_VERSION_MINOR=80 \
    JAVA_VERSION_BUILD=15 \
    JAVA_CHECKSUM=6152f8a7561acf795ca4701daa10a965 \
    JAVA_PACKAGE=jdk \
    JAVA_HOME=/opt/jdk \
    PATH=${PATH}:/opt/jdk/bin

RUN set -ex \
      && apk --no-cache add --virtual build-dependencies curl ca-certificates tar md5 \
      && curl --location --silent https://circle-artifacts.com/gh/andyshinn/alpine-pkg-glibc/6/artifacts/0/home/ubuntu/alpine-pkg-glibc/packages/x86_64/glibc-2.21-r2.apk > /tmp/glibc-2.21-r2.apk \
      && apk --update add --allow-untrusted /tmp/glibc-2.21-r2.apk \
      && mkdir /opt \
      && cd /opt \
      && curl -O --location --silent --insecure --show-error --junk-session-cookies \
          --header "Cookie: oraclelicense=accept-securebackup-cookie" \
          http://download.oracle.com/otn-pub/java/jdk/${JAVA_VERSION_MAJOR}u${JAVA_VERSION_MINOR}-b${JAVA_VERSION_BUILD}/${JAVA_PACKAGE}-${JAVA_VERSION_MAJOR}u${JAVA_VERSION_MINOR}-linux-x64.tar.gz \
      && echo ${JAVA_CHECKSUM}'  '${JAVA_PACKAGE}'-'${JAVA_VERSION_MAJOR}'u'${JAVA_VERSION_MINOR}'-linux-x64.tar.gz' | md5sum -c - \
      && tar -xzf ${JAVA_PACKAGE}-${JAVA_VERSION_MAJOR}u${JAVA_VERSION_MINOR}-linux-x64.tar.gz \
      && ln -s /opt/jdk1.${JAVA_VERSION_MAJOR}.0_${JAVA_VERSION_MINOR} /opt/jdk \
      && rm -rf /tmp/* \
          /opt/${JAVA_PACKAGE}-${JAVA_VERSION_MAJOR}u${JAVA_VERSION_MINOR}-linux-x64.tar.gz \
          /opt/jdk/*src.zip \
          /opt/jdk/lib/*javafx* \
          /opt/jdk/lib/missioncontrol \
          /opt/jdk/lib/visualvm \
          /opt/jdk/jre/bin/javaws \
          /opt/jdk/jre/lib/amd64/libdecora_sse.so \
          /opt/jdk/jre/lib/amd64/libprism_*.so \
          /opt/jdk/jre/lib/amd64/libfxplugins.so \
          /opt/jdk/jre/lib/amd64/libglass.so \
          /opt/jdk/jre/lib/amd64/libgstreamer-lite.so \
          /opt/jdk/jre/lib/amd64/libjavafx*.so \
          /opt/jdk/jre/lib/amd64/libjfx*.so \
          /opt/jdk/jre/lib/desktop \
          /opt/jdk/jre/lib/deploy* \
          /opt/jdk/jre/lib/ext/jfxrt.jar \
          /opt/jdk/jre/lib/*javafx* \
          /opt/jdk/jre/lib/javaws.jar \
          /opt/jdk/jre/lib/*jfx* \
          /opt/jdk/jre/lib/plugin.jar \
          /opt/jdk/jre/plugin \
      && apk del --purge build-dependencies
