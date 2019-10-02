FROM dimaskiddo/debian:base
MAINTAINER Dimas Restu Hidayanto <dimas.restu@student.upi.edu>

# Setting-up Environment
ENV MONGODB_VERSION 4.0

# Copying Prequisites Configuration
COPY ./content/ /usr/local/docker/

# Setting-up Permissions
RUN chmod 775 /usr/local/docker/bin/build \
  && /usr/local/docker/bin/build \
  && rm -f /usr/local/docker/bin/build

# Set Volumes Directory
VOLUME /var/lib/mongodb/data

# Expose Ports
EXPOSE 27017

# Set Entrypoint Script
ENTRYPOINT ["/usr/local/docker/bin/entrypoint"]

# Set Executor Script
CMD ["run-mongod"]

# Change Working User to "User"
USER user

# Set Labels Used in OpenShift to Describe the Builder Images
LABEL release=1 \
      vendor="Debian" \
      summary="Virtual Machine (VM) like container platform with MongoDB 4.0" \
      maintainer="Dimas Restu Hidayanto <dimas.restu@student.upi.edu>" \
      io.k8s.description="Debian (9.x) with MongoDB 4.0" \
      io.k8s.display-name="Debian (9.x) with MongoDB 4.0" \
      io.openshift.tags="builder,debian,mongodb" \
      io.openshift.expose-services="27017:mongodb" \
      io.openshift.non-scalable="false"
