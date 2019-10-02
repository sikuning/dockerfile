RabbitMQ 3.7 Image from Modified Base Image of Alpine. This image is ready to run using custom User ID with non-root user execution for OpenShift ready.

Build with love from Gegerkalong, Bandung, Indonesia.

**Maintainer:**

Dimas Restu H (<dimas.restu@student.upi.edu>)

**How to pull this image:**

> docker pull dimaskiddo/alpine:rabbitmq-3.7

**How to run this image:**

> docker run -p 4369:4369 -p 5671:5671 -p 5672:5672 -p 25672:25672 -v <local_data_path>:/var/lib/rabbitmq --name rabbitmq dimaskiddo/alpine:rabbitmq-3.7

**How to get in container after run this image:**

> docker exec -it rabbitmq /bin/bash
