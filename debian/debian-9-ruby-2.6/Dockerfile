FROM dimaskiddo/debian:base
MAINTAINER Dimas Restu Hidayanto <dimas.restu@student.upi.edu>

# Set Environment Variables
ENV LANG=C.UTF-8 \
    RUBY_MAJOR=2.6 \
    RUBY_VERSION=2.6.3 \
    BUNDLE_VERSION=2.0.2 \
    BUNDLE_PATH=/usr/local/bundle \
    BUNDLE_APP_CONFIG=/usr/local/bundle \
    BUNDLE_SILENCE_ROOT_WARNING=1 \
    GEM_HOME=/usr/local/bundle \
    PATH=$PATH:/usr/local/bundle/bin:/usr/local/bundle/gems/bin

# Copy Builder Files
COPY ./content/ /usr/local/docker/

# Run Builder Scripts
RUN chmod 775 /usr/local/docker/bin/build \
    && /usr/local/docker/bin/build \
    && rm -f /usr/local/docker/bin/build

# Set Labels Used in OpenShift to Describe the Builder Images
LABEL release=1 \
      vendor="Debian" \
      summary="Virtual Machine (VM) like container platform with Ruby 2.6" \
      maintainer="Dimas Restu Hidayanto <dimas.restu@student.upi.edu>" \
      io.k8s.description="Debian (9.x) Ruby 2.6" \
      io.k8s.display-name="Debian (9.x) Ruby 2.6" \
      io.openshift.tags="builder,debian,ruby" \
      io.openshift.non-scalable="false"