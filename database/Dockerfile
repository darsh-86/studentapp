FROM mysql
# Copy the custom MySQL configuration file
COPY mysql.cnf /etc/mysql/conf.d/mysql.cnf
# Copy initialization script to initialize database schema or seed data
COPY student.sql /docker-entrypoint-initdb.d/


