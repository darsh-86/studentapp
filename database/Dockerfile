FROM mysql:latest
ENV V MYSQL_ROOT_PASSWORD="1234"
ENV MYSQL_DATABASE="studentapp"
COPY student.sql /docker-entrypoint-initdb.d/
EXPOSE 3306
CMD ["mysqld"]
