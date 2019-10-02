FROM dimaskiddo/alpine:base
MAINTAINER Dimas Restu Hidayanto <dimas.restu@student.upi.edu>

# Set Environment Variables
ENV LANG=C.UTF-8 \
    GO_VERSION=1.11.13 \
    GOOS=linux \
    GOPATH=/usr/src/go \
    PATH=$PATH:/usr/local/go/bin:/usr/src/go/bin

# Copying Prequisites Configuration
COPY ./content/ /usr/local/docker/

# Setting-up Permissions
RUN chmod 775 /usr/local/docker/bin/build \
  && /usr/local/docker/bin/build \
  && rm -f /usr/local/docker/bin/build

# Set Labels Used in OpenShift to Describe the Builder Images
LABEL release=1 \
      vendor="Alpine" \
      summary="Virtual Machine (VM) like container platform with Go 1.11" \
      maintainer="Dimas Restu Hidayanto <dimas.restu@student.upi.edu>" \
      io.k8s.description="Alpine (3.x) with Go 1.11" \
      io.k8s.display-name="Alpine (3.x) with Go 1.11" \
      io.openshift.tags="builder,alpine,go" \
      io.openshift.non-scalable="false"
