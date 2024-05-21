FROM mysql:latest
<<<<<<< HEAD
ENV MYSQL_ROOT_PASSWORD="darsh@4321"
ENV MYSQL_DATABASE="studentapp"
COPY student.sql /docker-entrypoint-initdb.d/
=======

# Set MySQL root password from Kubernetes secret
ARG MYSQL_ROOT_PASSWORD
ENV MYSQL_ROOT_PASSWORD=$MYSQL_ROOT_PASSWORD

# Set MySQL database name from Kubernetes secret
ARG MYSQL_DATABASE
ENV MYSQL_DATABASE=$MYSQL_DATABASE

# Copy initialization script to initialize database schema or seed data
COPY student.sql /docker-entrypoint-initdb.d/
>>>>>>> b4279cc2108bd9f65ef2509b096d5ab4b65b6491