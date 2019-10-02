FROM dimaskiddo/alpine:nodejs-8.9.3
MAINTAINER Dimas Restu Hidayanto <dimas.restu@student.upi.edu>

# Set Environment Variables
ENV CHROME_BIN=/usr/bin/chromium-browser \
    CHROME_PATH=/usr/lib/chromium

ENV PUPPETEER_VERSION=1.12.2 \
    PUPPETEER_EXECUTABLE_PATH=${CHROME_BIN} \
    PUPPETEER_SKIP_CHROMIUM_DOWNLOAD=true

# Copy Builder Files
COPY ./content/ /usr/local/docker/

# Run Builder Scripts
RUN chmod 775 /usr/local/docker/bin/build \
    && /usr/local/docker/bin/build \
    && rm -f /usr/local/docker/bin/build

# Set Entrypoint Script
ENTRYPOINT ["/usr/local/docker/bin/entrypoint"]

# Set Labels Used in OpenShift to Describe the Builder Images
LABEL release=1 \
      vendor="Alpine" \
      summary="Virtual Machine (VM) like container platform with Puppeteer 1.12.2" \
      maintainer="Dimas Restu Hidayanto <dimas.restu@student.upi.edu>" \
      io.k8s.description="Alpine (3.x) NodeJS 8.9.3 with Puppeteer 1.12.2" \
      io.k8s.display-name="Alpine (3.x) NodeJS 8.9.3 with Puppeteer 1.12.2" \
      io.openshift.tags="builder,alpine,nodejs,puppeteer" \
      io.openshift.non-scalable="false"