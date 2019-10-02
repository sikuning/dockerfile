FROM dimaskiddo/alpine:base
MAINTAINER Dimas Restu Hidayanto <dimas.restu@student.upi.edu>

# Set Environment Variables
ENV APM_VERSION=6.5.4 \
    APM_HOME=/opt/apm-server \
    PATH=$PATH:/opt/apm-server

# Copying Prequisites Configuration
COPY ./content/ /usr/local/docker/

# Setting-up Permissions
RUN chmod 775 /usr/local/docker/bin/build \
  && /usr/local/docker/bin/build \
  && rm -f /usr/local/docker/bin/build

# Expose Ports
EXPOSE 8200

# Set Entrypoint Script
ENTRYPOINT ["/usr/local/docker/bin/entrypoint"]

# Set Executor Script
CMD ["sh","-c","apm-server ${APM_ARGS}"]

# Change Working User to "User"
USER user

# Change Working Directory to APM Home Directory
WORKDIR ${APM_HOME}

# Set Labels Used in OpenShift to Describe the Builder Images
LABEL release=1 \
      vendor="Alpine" \
      summary="Virtual Machine (VM) like container platform with APM 6.5" \
      maintainer="Dimas Restu Hidayanto <dimas.restu@student.upi.edu>" \
      io.k8s.description="Alpine (3.x) with APM 6.5" \
      io.k8s.display-name="Alpine (3.x) with APM 6.5" \
      io.openshift.tags="builder,alpine,apm" \
      io.openshift.expose-services="8200:apm" \
      io.openshift.non-scalable="false"
