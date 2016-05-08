# BusyBox with a glibc and Oracle Java 8
FROM armhf/busybox:glibc

MAINTAINER James Bacon james@baconi.co.uk

# Java Version and other ENV
ENV JAVA_VERSION_MAJOR=8 \
    JAVA_VERSION_MINOR=91 \
    JAVA_VERSION_BUILD=14

RUN mkdir -p /usr/lib/jvm && \
    curl -jksSLH "Cookie: oraclelicense=accept-securebackup-cookie" -o /tmp/java.tar.gz \
      "http://download.oracle.com/otn-pub/java/jdk/${JAVA_VERSION_MAJOR}u${JAVA_VERSION_MINOR}-b${JAVA_VERSION_BUILD}/jdk-${JAVA_VERSION_MAJOR}u${JAVA_VERSION_MINOR}-linux-arm32-vfp-hflt.tar.gz" && \

    # Extract
    tar -C /usr/lib/jvm -xzvf /tmp/java.tar.gz && \

    # Reduce
    rm -rf /tmp/* /var/cache/apk/*

# Define working directory.
#WORKDIR /data

# Define commonly used JAVA_HOME variable
ENV JAVA_HOME=/usr/lib/jvm/java-8-oracle

#CMD [""]