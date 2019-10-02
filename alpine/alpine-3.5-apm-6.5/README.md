APM 6.5 Image from Modified Base Image of Alpine. This image is ready to run using custom User ID with non-root user execution for OpenShift ready.

Build with love from Gegerkalong, Bandung, Indonesia.

**Maintainer:**

Dimas Restu H (<dimas.restu@student.upi.edu>)

**How to pull this image:**

> docker pull dimaskiddo/alpine:apm-6.5

**How to run this image:**

> docker run -p 8200:8200 --name apm dimaskiddo/alpine:apm-6.5

**How to get in container after run this image:**

> docker exec -it apmserver /bin/bash
