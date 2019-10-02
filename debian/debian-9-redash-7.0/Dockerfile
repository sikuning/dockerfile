FROM dimaskiddo/debian:python-2.7
MAINTAINER Dimas Restu Hidayanto <dimas.restu@student.upi.edu>

# Setting-up Arguments
ARG skip_ds_deps

# Setting-up Environment
ENV REDASH_VERSION=7.0.0 \
    REDASH_HOMR=/opt/redash \
    PATH=$PATH:/opt/redash/bin

# Change Working Directory to Application Source Directory
WORKDIR /opt/redash

# Copy ReDash Python Requirements
COPY requirements.txt requirements_dev.txt requirements_all_ds.txt /opt/redash/

# Install ReDash Dependencies
RUN apt-get -y -o Acquire::Check-Valid-Until=false update \
    && apt-get -y -o Acquire::Check-Valid-Until=false --no-install-recommends install \
        build-essential \
        xmlsec1 \
        libaio-dev \
        libev-dev \
        libffi-dev \
        libssl-dev \
        libsasl2-dev \
        libpq-dev \
        default-libmysqlclient-dev \
        freetds-dev \
    && apt-get -y -o Acquire::Check-Valid-Until=false autoremove \
    && apt-get -y -o Acquire::Check-Valid-Until=false clean \
    && pip install --no-cache-dir -r requirements.txt \
    && pip install --no-cache-dir -r requirements_dev.txt \
    && if [ "x$skip_ds_deps" = "x" ]; then pip install --no-cache-dir -r requirements_all_ds.txt; else echo "Skipping pip install --no-cache-dir -r requirements_all_ds.txt"; fi \
    && apt-get -y -o Acquire::Check-Valid-Until=false -o APT::AutoRemove::RecommendsImportant=false -o APT::AutoRemove::SuggestsImportant=false --auto-remove purge \
        build-essential \
        libaio-dev \
        libev-dev \
        libffi-dev \
        libssl-dev \
        libsasl2-dev \
    && apt-get -y -o Acquire::Check-Valid-Until=false autoremove \
    && apt-get -y -o Acquire::Check-Valid-Until=false clean

# Copy ReDash Application
COPY . /opt/redash/

# Make ReDash Binaries Executable
RUN chown -R root:root /opt/redash \
    && chmod -R 775 /opt/redash

# Set Entrypoint Script
ENTRYPOINT ["/opt/redash/bin/redash"]

# Set Executor Script
CMD ["server"]

# Change Working User to "User"
USER user

# Set Labels Used in OpenShift to Describe the Builder Images
LABEL release=1 \
      vendor="Debian" \
      summary="Virtual Machine (VM) like container platform with ReDash 7.0" \
      maintainer="Dimas Restu Hidayanto <dimas.restu@student.upi.edu>" \
      io.k8s.description="Debian (9.x) Python 2.7 with ReDash 7.0" \
      io.k8s.display-name="Debian (9.x) Python 2.7 with ReDash 7.0" \
      io.openshift.tags="builder,debian,python,redash" \
      io.openshift.non-scalable="false"