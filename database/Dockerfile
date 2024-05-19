FROM mysql

# Set MySQL root password from Kubernetes secret
ENV MYSQL_ROOT_PASSWORD=$MYSQL_ROOT_PASSWORD
ENV MYSQL_DATABASE=$MYSQL_DATABASE

# Copy initialization script to initialize database schema or seed data
COPY student.sql /docker-entrypoint-initdb.d/


