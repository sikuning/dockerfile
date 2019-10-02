FROM dimaskiddo/alpine:base
MAINTAINER Dimas Restu Hidayanto <dimas.restu@student.upi.edu>

# Setting-up Environment
ENV FILEBROWSER_VERSION 2.0.12

# Copying Prequisites Configuration
COPY ./content/ /usr/local/docker/

# Setting-up Permissions
RUN chmod 775 /usr/local/docker/bin/build \
  && /usr/local/docker/bin/build \
  && rm -f /usr/local/docker/bin/build

# Set Volumes Directory
VOLUME /data/filebrowser

# Expose Ports
EXPOSE 8080

# Set Entrypoint Script
ENTRYPOINT ["/usr/local/docker/bin/entrypoint"]

# Set Executor Script
CMD ["filebrowser"]

# Change Working User to "User"
USER user

# Set Labels Used in OpenShift to Describe the Builder Images
LABEL release=1 \
      vendor="Alpine" \
      summary="Virtual Machine (VM) like container platform with File Browser 2.0" \
      maintainer="Dimas Restu Hidayanto <dimas.restu@student.upi.edu>" \
      io.k8s.description="Alpine (3.x) with File Browser 2.0" \
      io.k8s.display-name="Alpine (3.x) with File Browser 2.0" \
      io.openshift.tags="builder,alpine,filebrowser" \
      io.openshift.expose-services="8080:filebrowser-http" \
      io.openshift.non-scalable="false"
