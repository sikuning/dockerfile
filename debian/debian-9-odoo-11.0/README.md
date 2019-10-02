Odoo 11.0 Image from Modified Base Image of Debian. This image is ready to run using custom User ID with non-root user execution for OpenShift ready.

Build with love from Gegerkalong, Bandung, Indonesia.

**Maintainer:**

Dimas Restu H (<dimas.restu@student.upi.edu>)

**How to pull this image:**

> docker pull dimaskiddo/debian:odoo-11.0

**How to run this image:**

> docker run -p 8069:8069 -v <local_data_path>:/var/lib/odoo --name odoo dimaskiddo/debian:odoo-11.0

**How to get in container after run this image:**

> docker exec -it odoo /bin/bash
