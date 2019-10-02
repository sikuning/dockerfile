Python 3.6 with uWSGI 2.0 Image from Modified Base Image of Alpine
This Image is ready to serve with custom User ID execution using entrypoint script.

Build with love from Gegerkalong, Bandung, Indonesia.

**Maintainer:**

Dimas Restu H (<dimas.restu@student.upi.edu>)

**How to pull this image:**

> docker pull dimaskiddo/alpine:python-3.6-uwsgi

**How to run this image:**

> docker run -p 80:8080 --name uwsgi dimaskiddo/alpine:python-3.6-uwsgi

**How to get in container after run this image:**

> docker exec -it uwsgi /bin/bash
