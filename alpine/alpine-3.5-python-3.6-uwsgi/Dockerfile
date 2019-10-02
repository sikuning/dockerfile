FROM dimaskiddo/alpine:python-3.6
MAINTAINER Dimas Restu Hidayanto <dimas.restu@student.upi.edu>

# Set Environment Variables
ENV UWSGI_CHEAPER=4 \
    UWSGI_PROCESSES=16 \
    UWSGI_INI=/etc/uwsgi/python.ini

# Copy Builder Files
COPY ./content/ /usr/local/docker/

# Run Builder Scripts
RUN chmod 775 /usr/local/docker/bin/build \
    && /usr/local/docker/bin/build \
    && rm -f /usr/local/docker/bin/build

# Expose Ports
EXPOSE 8080 8443

# Set Entrypoint Script
ENTRYPOINT ["/usr/local/docker/bin/entrypoint"]

# Set Executor Script
CMD ["/usr/bin/supervisord","-n","-c","/etc/supervisor/supervisord.conf","-d","/etc/supervisor"]

# Set Labels Used in OpenShift to Describe the Builder Images
LABEL release=1 \
      vendor="Alpine" \
      summary="Virtual Machine (VM) like container platform with Python 3.6 with uWSGI 2.0" \
      maintainer="Dimas Restu Hidayanto <dimas.restu@student.upi.edu>" \
      io.k8s.description="Alpine (3.x) Python 3.6 with uWSGI 2.0" \
      io.k8s.display-name="Alpine (3.x) Python 3.6 with uWSGI 2.0" \
      io.openshift.tags="builder,alpine,python,uwsgi" \
      io.openshift.expose-services="8080:http,8443:https" \
      io.openshift.non-scalable="false"