# OpenJDK v11.0.5
# docker run --rm pottava/java:10

FROM alpine:3.11

RUN apk --no-cache add "openjdk10=10.0.2_p13-r0"

ENV JAVA_HOME=/usr/lib/jvm/default-jvm/jre
CMD ["/usr/bin/java", "-version"]
