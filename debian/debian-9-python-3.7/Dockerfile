FROM dimaskiddo/debian:base
MAINTAINER Dimas Restu Hidayanto <dimas.restu@student.upi.edu>

# Set Environment Variables
ENV LANG=C.UTF-8 \
    PYTHONIOENCODING=UTF-8 \
    PYTHON_VERSION=3.7.4 \
    PYTHON_GPG_KEY=0D96DF4D4110E5C43FBFB17F2D347EA6AA65421D

# Copy Builder Files
COPY ./content/ /usr/local/docker/

# Run Builder Scripts
RUN chmod 775 /usr/local/docker/bin/build \
    && /usr/local/docker/bin/build \
    && rm -f /usr/local/docker/bin/build

# Set Labels Used in OpenShift to Describe the Builder Images
LABEL release=1 \
      vendor="Debian" \
      summary="Virtual Machine (VM) like container platform with Python 3.7" \
      maintainer="Dimas Restu Hidayanto <dimas.restu@student.upi.edu>" \
      io.k8s.description="Debian (9.x) Python 3.7" \
      io.k8s.display-name="Debian (9.x) Python 3.7" \
      io.openshift.tags="builder,debian,python" \
      io.openshift.non-scalable="false"