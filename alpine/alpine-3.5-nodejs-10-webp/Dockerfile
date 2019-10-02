FROM dimaskiddo/alpine:nodejs-10
MAINTAINER Dimas Restu Hidayanto <dimas.restu@student.upi.edu>

# Set Environment Variables
ENV WEBP_VERSION 1.0.3

# Copy Builder Files
COPY ./content/ /usr/local/docker/

# Run Builder Scripts
RUN chmod 775 /usr/local/docker/bin/build \
    && /usr/local/docker/bin/build \
    && rm -f /usr/local/docker/bin/build

# Set Labels Used in OpenShift to Describe the Builder Images
LABEL release=1 \
      vendor="Alpine" \
      summary="Virtual Machine (VM) like container platform with WEBP 1.0.3" \
      maintainer="Dimas Restu Hidayanto <dimas.restu@student.upi.edu>" \
      io.k8s.description="Alpine (3.x) NodeJS 10 with WEBP 1.0.3" \
      io.k8s.display-name="Alpine (3.x) NodeJS 10 with WEBP 1.0.3" \
      io.openshift.tags="builder,alpine,nodejs,webp" \
      io.openshift.non-scalable="false"