FROM dimaskiddo/alpine:rabbitmq-3.7
MAINTAINER Dimas Restu Hidayanto <dimas.restu@student.upi.edu>

# Change Working User to "Root"
USER root

# Copy Builder Files
COPY ./content/ /usr/local/docker/

# Run Builder Scripts
RUN chmod 775 /usr/local/docker/bin/build \
    && /usr/local/docker/bin/build \
    && rm -f /usr/local/docker/bin/build

# Expose Ports
EXPOSE 15671 15672

# Change Working User to "User"
USER user

# Set Labels Used in OpenShift to Describe the Builder Images
LABEL release=1 \
      vendor="Alpine" \
      summary="Virtual Machine (VM) like container platform with RabbitMQ 3.7 Management" \
      maintainer="Dimas Restu Hidayanto <dimas.restu@student.upi.edu>" \
      io.k8s.description="Alpine (3.x) Erlang 22 with RabbitMQ 3.7 Management" \
      io.k8s.display-name="Alpine (3.x) Erlang 22 with RabbitMQ 3.7 Management" \
      io.openshift.tags="builder,alpine,erlang,rabbitmq" \
      io.openshift.expose-services="4369:rabbitmq-epmd;5671:rabbitmq-amqp-tls;5672:rabbitmq-amqp;25672:rabbitmq-internode;15671:rabbitmq-management-ssl;15672:rabbitmq-management" \
      io.openshift.non-scalable="false"