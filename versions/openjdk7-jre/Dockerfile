# OpenJDK v1.7.0_91 (JRE)
# docker run --rm pottava/java:7-jre

FROM alpine:3.4

RUN apk --no-cache add openjdk7-jre

ENV JAVA_HOME=/usr/lib/jvm/default-jvm/jre
CMD ["/usr/bin/java", "-version"]
