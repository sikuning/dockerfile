FROM dimaskiddo/alpine-latest:base
MAINTAINER Dimas Restu Hidayanto <dimas.restu@student.upi.edu>

# Set Environment Variables
ENV LANG=C.UTF-8 \
    NODE_VERSION=8.16.1 \
    YARN_VERSION=1.17.3

# Copy Builder Files
COPY ./content/ /usr/local/docker/

# Run Builder Scripts
RUN chmod 775 /usr/local/docker/bin/build \
    && /usr/local/docker/bin/build \
    && rm -f /usr/local/docker/bin/build

# Set Labels Used in OpenShift to Describe the Builder Images
LABEL release=1 \
      vendor="Alpine" \
      summary="Virtual Machine (VM) like container platform with NodeJS 8" \
      maintainer="Dimas Restu Hidayanto <dimas.restu@student.upi.edu>" \
      io.k8s.description="Alpine (3.x) NodeJS 8" \
      io.k8s.display-name="Alpine (3.x) NodeJS 8" \
      io.openshift.tags="builder,alpine,nodejs" \
      io.openshift.non-scalable="false"