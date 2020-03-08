# OpenJDK v11.0.5
# docker run --rm pottava/java:11

FROM alpine:3.11

RUN apk --no-cache add "openjdk11=11.0.5_p10-r0"

ENV JAVA_HOME=/usr/lib/jvm/default-jvm/jre
CMD ["/usr/bin/java", "-version"]
