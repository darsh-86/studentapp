FROM tomcat:9.0-slim

# Set the working directory
WORKDIR /opt

# Define environment variables
ENV APP_HOME=/usr/local/tomcat
ENV PORT=8080

# Add the application WAR file and MySQL connector JAR
ADD https://webapp2-akashapp.s3.amazonaws.com/student.war $APP_HOME/webapps/
ADD https://webapp-akash.s3.amazonaws.com/mysql-connector-j-8.3.0.jar $APP_HOME/lib

# Copy the config directory to /opt
COPY config /opt

# Modify the context.xml with configuration from /opt/config
RUN sed -i '20r /opt/config' $APP_HOME/conf/context.xml

# Expose the application port
EXPOSE $PORT

# Start Tomcat
CMD ["catalina.sh", "run"]
