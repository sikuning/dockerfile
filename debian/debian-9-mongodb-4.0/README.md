MongoDB 4.0 Image from Modified Base Image of Debian. This image is ready to run using custom User ID with non-root user execution for OpenShift ready.

Build with love from Gegerkalong, Bandung, Indonesia.

**Maintainer:**

Dimas Restu H (<dimas.restu@student.upi.edu>)

**How to pull this image:**

> docker pull dimaskiddo/debian:mongodb-4.0

**How to run this image:**

> docker run -p 27017:27017 -v <local_data_path>:/var/lib/mongodb/data --name mongodb dimaskiddo/debian:mongodb-4.0

**How to get in container after run this image:**

> docker exec -it mongodb /bin/bash
