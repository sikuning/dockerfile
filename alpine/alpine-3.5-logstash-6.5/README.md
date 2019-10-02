LogStash 6.5 Image from Modified Base Image of Alpine. This image is ready to run using custom User ID with non-root user execution for OpenShift ready.

Build with love from Gegerkalong, Bandung, Indonesia.

**Maintainer:**

Dimas Restu H (<dimas.restu@student.upi.edu>)

**How to pull this image:**

> docker pull dimaskiddo/alpine:logstash-6.5

**How to run this image:**

> docker run -p 9600:9600 -p 5000:5000 --name logstash dimaskiddo/alpine:logstash-6.5

**How to get in container after run this image:**

> docker exec -it logstash /bin/bash
