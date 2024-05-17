FROM tomcat:9.0-slim

WORKDIR /opt

ENV APP_HOME=/usr/local/tomcat
ENV PORT=8080

ADD https://webapp2-akashapp.s3.amazonaws.com/student.war $APP_HOME/webapps/

ADD https://webapp-akash.s3.amazonaws.com/mysql-connector-j-8.3.0.jar $APP_HOME/lib

COPY config /opt

RUN sed -i '20r /opt/config' $APP_HOME/conf/context.xml

EXPOSE $PORT

CMD ["catalina.sh", "run"]
