Nginx 1.16 + PHP 7.1 + PHP Composer Image from Modified Base Image of Debian. This image is ready to run using custom User ID with non-root user execution for OpenShift ready.

Build with love from Gegerkalong, Bandung, Indonesia.

**Maintainer:**

Dimas Restu H (<dimas.restu@student.upi.edu>)

**How to pull this image:**

> docker pull dimaskiddo/debian:php-7.1-nginx

**How to run this image:**

> docker run -p 8080:8080 -p 8443:8443 -v <local_data_path>:/var/www --name php dimaskiddo/debian:php-7.1-nginx

**How to get in container after run this image:**

> docker exec -it php /bin/bash
