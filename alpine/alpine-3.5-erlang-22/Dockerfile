FROM dimaskiddo/alpine:base
MAINTAINER Dimas Restu Hidayanto <dimas.restu@student.upi.edu>

# Set Environment Variables
ENV LANG=C.UTF-8 \
    ERLANG_VERSION=22.0.7 \
    REBAR3_VERSION=3.11.1

# Copy Builder Files
COPY ./content/ /usr/local/docker/

# Run Builder Scripts
RUN chmod 775 /usr/local/docker/bin/build \
    && /usr/local/docker/bin/build \
    && rm -f /usr/local/docker/bin/build

# Set Labels Used in OpenShift to Describe the Builder Images
LABEL release=1 \
      vendor="Alpine" \
      summary="Virtual Machine (VM) like container platform with Erlang 22" \
      maintainer="Dimas Restu Hidayanto <dimas.restu@student.upi.edu>" \
      io.k8s.description="Alpine (3.x) Erlang 22" \
      io.k8s.display-name="Alpine (3.x) Erlang 22" \
      io.openshift.tags="builder,alpine,erlang" \
      io.openshift.non-scalable="false"