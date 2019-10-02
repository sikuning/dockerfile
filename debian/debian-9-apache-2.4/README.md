Apache 2.4 Image from Modified Base Image of Debian. This image is ready to run using custom User ID with non-root user execution for OpenShift ready.

Build with love from Gegerkalong, Bandung, Indonesia.

**Maintainer:**

Dimas Restu H (<dimas.restu@student.upi.edu>)

**How to pull this image:**

> docker pull dimaskiddo/debian:apache-2.4

**How to run this image:**

> docker run -p 8080:8080 -p 8443:8443 -v <local_data_path>:/var/www --name apache dimaskiddo/debian:apache-2.4

**How to get in container after run this image:**

> docker exec -it apache /bin/bash
