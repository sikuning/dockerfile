FROM dimaskiddo/alpine:openjre-8.0
MAINTAINER Dimas Restu Hidayanto <dimas.restu@student.upi.edu>

# Set Environment Variables
ENV LS_VERSION=6.5.4 \
    LS_GPG_KEY=46095ACC8548582C1A2699A9D27D666CD88E42B4 \
    LS_HOME=/opt/logstash \
    LS_SETTINGS_DIR=/opt/logstash/config \
    PATH=$PATH:/opt/logstash/bin

# Copying Prequisites Configuration
COPY ./content/ /usr/local/docker/

# Setting-up Permissions
RUN chmod 775 /usr/local/docker/bin/build \
  && /usr/local/docker/bin/build \
  && rm -f /usr/local/docker/bin/build

# Set Volumes Directory
VOLUME /opt/logstash/data

# Expose Ports
EXPOSE 9600 5000

# Set Entrypoint Script
ENTRYPOINT ["/usr/local/docker/bin/entrypoint"]

# Set Executor Script
CMD ["logstash"]

# Change Working User to "User"
USER user

# Set Labels Used in OpenShift to Describe the Builder Images
LABEL release=1 \
      vendor="Alpine" \
      summary="Virtual Machine (VM) like container platform with LogStash 6.5" \
      maintainer="Dimas Restu Hidayanto <dimas.restu@student.upi.edu>" \
      io.k8s.description="Alpine (3.x) with LogStash 6.5" \
      io.k8s.display-name="Alpine (3.x) with LogStash 6.5" \
      io.openshift.tags="builder,alpine,logstash" \
      io.openshift.expose-services="9600:logstash-http,5000:logstash-transport" \
      io.openshift.non-scalable="false"
