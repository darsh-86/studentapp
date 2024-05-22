FROM mysql:latest

# Copy the custom MySQL configuration file
COPY mysql.cnf /etc/mysql/conf.d/

# Ensure the configuration is loaded correctly
CMD ["mysqld"]
