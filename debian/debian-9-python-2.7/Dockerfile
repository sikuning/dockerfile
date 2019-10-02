FROM dimaskiddo/debian:base
MAINTAINER Dimas Restu Hidayanto <dimas.restu@student.upi.edu>

# Set Environment Variables
ENV LANG=C.UTF-8 \
    PYTHONIOENCODING=UTF-8 \
    PYTHON_VERSION=2.7.16 \
    PYTHON_GPG_KEY=C01E1CAD5EA2C4F0B8E3571504C367C218ADD4FF

# Copy Builder Files
COPY ./content/ /usr/local/docker/

# Run Builder Scripts
RUN chmod 775 /usr/local/docker/bin/build \
    && /usr/local/docker/bin/build \
    && rm -f /usr/local/docker/bin/build

# Set Labels Used in OpenShift to Describe the Builder Images
LABEL release=1 \
      vendor="Debian" \
      summary="Virtual Machine (VM) like container platform with Python 2.7" \
      maintainer="Dimas Restu Hidayanto <dimas.restu@student.upi.edu>" \
      io.k8s.description="Debian (9.x) Python 2.7" \
      io.k8s.display-name="Debian (9.x) Python 2.7" \
      io.openshift.tags="builder,debian,python" \
      io.openshift.non-scalable="false"