FROM dimaskiddo/alpine:erlang-22
MAINTAINER Dimas Restu Hidayanto <dimas.restu@student.upi.edu>

# Set Environment Variables
ENV RABBITMQ_VERSION=3.7.17 \
    RABBITMQ_GPG_KEY="0x0A9AF2115F4687BD29803A206B73A36E6026DFCA" \
    RABBITMQ_DATA_DIR=/var/lib/rabbitmq \
    RABBITMQ_HOME=/opt/rabbitmq \
    RABBITMQ_LOGS=- \
    RABBITMQ_SASL_LOGS=- \
    PATH=$PATH:/opt/rabbitmq/sbin

# Copy Builder Files
COPY ./content/ /usr/local/docker/

# Run Builder Scripts
RUN chmod 775 /usr/local/docker/bin/build \
    && /usr/local/docker/bin/build \
    && rm -f /usr/local/docker/bin/build

# Set Volumes Directory
VOLUME /var/lib/rabbitmq

# Expose Ports
EXPOSE 4369 5671 5672 25672

# Set Entrypoint Script
ENTRYPOINT ["/usr/local/docker/bin/entrypoint"]

# Set Executor Script
CMD ["rabbitmq-server"]

# Change Working User to "User"
USER user

# Set Labels Used in OpenShift to Describe the Builder Images
LABEL release=1 \
      vendor="Alpine" \
      summary="Virtual Machine (VM) like container platform with RabbitMQ 3.7" \
      maintainer="Dimas Restu Hidayanto <dimas.restu@student.upi.edu>" \
      io.k8s.description="Alpine (3.x) Erlang 22 with RabbitMQ 3.7" \
      io.k8s.display-name="Alpine (3.x) Erlang 22 with RabbitMQ 3.7" \
      io.openshift.tags="builder,alpine,erlang,rabbitmq" \
      io.openshift.expose-services="4369:rabbitmq-epmd;5671:rabbitmq-amqp-tls;5672:rabbitmq-amqp;25672:rabbitmq-internode" \
      io.openshift.non-scalable="false"