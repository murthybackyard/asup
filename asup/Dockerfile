#
# Build test
#
FROM maven:3.5-jdk-8 AS build
COPY src /home/app/src
COPY pom.xml /home/app
RUN mvn -f /home/app/pom.xml clean package

#
# Package test
#

    
#FROM openjdk:8-jre-slim
#COPY --from=build /home/app/target/asup.war /home/asup.war

FROM tomcat:8.5.38-jre8

COPY --from=build /home/app/target/. /usr/local/tomcat/webapps/

#RUN unzip /usr/local/tomcat/webapps/webapp/asup.war

CMD ["catalina.sh", "run"]


#EXPOSE 8888:8080
#ENTRYPOINT ["index.jsp"]