FROM dimaskiddo/alpine:python-3.6-scipy
MAINTAINER Dimas Restu Hidayanto <dimas.restu@student.upi.edu>

# Set Environment Variables
ENV PANDAS_VERSION 0.24.2

# Copy Builder Files
COPY ./content/ /usr/local/docker/

# Run Builder Scripts
RUN chmod 775 /usr/local/docker/bin/build \
    && /usr/local/docker/bin/build \
    && rm -f /usr/local/docker/bin/build

# Set Labels Used in OpenShift to Describe the Builder Images
LABEL release=1 \
      vendor="Alpine" \
      summary="Virtual Machine (VM) like container platform with Pandas 0.24" \
      maintainer="Dimas Restu Hidayanto <dimas.restu@student.upi.edu>" \
      io.k8s.description="Alpine (3.x) Python 3.6 with Pandas 0.24" \
      io.k8s.display-name="Alpine (3.x) Python 3.6 with Pandas 0.24" \
      io.openshift.tags="builder,alpine,python,pandas" \
      io.openshift.non-scalable="false"