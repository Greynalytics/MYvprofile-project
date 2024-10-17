FROM openjdk:11 AS BUILD_IMAGE
LABEL "project"="MYvprofile"
LABEL "Author"="Greynalytics"
RUN apt update && apt install maven -y
RUN git clone https://github.com/Greynalytics/MYvprofile-project.git
RUN cd MYvprofile-project && git checkout docker && mvn install

FROM tomcat:9-jre11
RUN rm -rf /usr/local/tomcat/webapps/*
COPY --from=BUILD_IMAGE MYvprofile-project/target/vprofile-v2.war/usr/local/tomcat/webapps/ROOT.war

EXPOSE 8080
CMD ["catalina.sh", "run"]