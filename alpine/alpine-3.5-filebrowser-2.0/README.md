File Browser 2.0 Image from Modified Base Image of Alpine. This image is ready to run using custom User ID with non-root user execution for OpenShift ready.

Build with love from Gegerkalong, Bandung, Indonesia.

**Maintainer:**

Dimas Restu H (<dimas.restu@student.upi.edu>)

**How to pull this image:**

> docker pull dimaskiddo/alpine:filebrowser-2.0

**How to run this image:**

> docker run -p 8080:8080 -v <local_data_path>:/data/filebrowser --name filebrowser dimaskiddo/alpine:filebrowser-2.0

**How to get in container after run this image:**

> docker exec -it filebrowser /bin/bash
