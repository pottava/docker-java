# OpenJDK v1.8.0_111 (JRE)
# docker run --rm pottava/java:8-jre

FROM alpine:3.5

RUN apk --no-cache add openjdk8-jre

ENV JAVA_HOME=/usr/lib/jvm/default-jvm/jre
CMD ["/usr/bin/java", "-version"]
