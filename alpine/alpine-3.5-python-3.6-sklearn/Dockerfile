FROM dimaskiddo/alpine:python-3.6-scipy
MAINTAINER Dimas Restu Hidayanto <dimas.restu@student.upi.edu>

# Set Environment Variables
ENV CYTHON_VERSION=0.29.13 \
    SKLEARN_VERSION=0.0

# Copy Builder Files
COPY ./content/ /usr/local/docker/

# Run Builder Scripts
RUN chmod 775 /usr/local/docker/bin/build \
    && /usr/local/docker/bin/build \
    && rm -f /usr/local/docker/bin/build

# Set Labels Used in OpenShift to Describe the Builder Images
LABEL release=1 \
      vendor="Alpine" \
      summary="Virtual Machine (VM) like container platform with SKLearn 0.0" \
      maintainer="Dimas Restu Hidayanto <dimas.restu@student.upi.edu>" \
      io.k8s.description="Alpine (3.x) Python 3.6 with SKLearn 0.0" \
      io.k8s.display-name="Alpine (3.x) Python 3.6 with SKLearn 0.0" \
      io.openshift.tags="builder,alpine,python,sklearn" \
      io.openshift.non-scalable="false"