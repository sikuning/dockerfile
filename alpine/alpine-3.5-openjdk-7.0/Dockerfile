FROM dimaskiddo/alpine:base
MAINTAINER Dimas Restu Hidayanto <dimas.restu@student.upi.edu>

# Set Environment Variables
ENV LANG=C.UTF-8 \
    JAVA_HOME=/usr/lib/jvm/java-1.7-openjdk \
    PATH=$PATH:/usr/lib/jvm/java-1.7-openjdk/bin:/usr/lib/jvm/java-1.7-openjdk/jre/bin

# Copy Builder Files
COPY ./content/ /usr/local/docker/

# Run Builder Scripts
RUN chmod 775 /usr/local/docker/bin/build \
    && /usr/local/docker/bin/build \
    && rm -f /usr/local/docker/bin/build
