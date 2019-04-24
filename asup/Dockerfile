#
# Build test
#
FROM maven:3.5-jdk-8 AS build
COPY src /home/app/src
COPY pom.xml /home/app
RUN mvn -f /home/app/pom.xml clean package


FROM tomcat:8.5.38-jre8
COPY --from=build /home/app/target/. /usr/local/tomcat/webapps/
CMD ["catalina.sh", "run"]