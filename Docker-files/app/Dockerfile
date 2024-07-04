FROM openjdk:11 AS BUILD_IMAGE
RUN apt update && apt install maven -y
RUN git clone https://github.com/Ningg-gg/vprofile-project.git 
RUN cd vprofile-project && git checkout docker && mvn install
# git clone: to clone the source code
# cd vproffile-project: to go to that folder and git checkout docker: to switch branch and mvn install: to generate the artiffact in the vprofile folder
# in the vprofile-project, we will have a Targer folder and in that, we will have the artifact, vprofile-v2.war

FROM tomcat:9-jre11
LABEL "Project"="Vprofile"
LABEL "Author"="Janrey"
RUN rm -rf /usr/local/tomcat/webapps/* 
COPY --from=BUILD_IMAGE vprofile-project/target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war
# rm -rf to remove the default the tomcat application/ we will then copy the artifact to replace the default artifact of tomcat
#/usr/local/tomcat/webapps/*  is the tomcat working directory
# /usr/local/tomcat//webapps is where the default tomcat application. info can be found in the image documentation in the dockerhub.
#COPY to copy the artifact that was created in the first stage. 
# vprofile-project/target/vprofile-v2.war is the one we will be copying and the destination is /usr/local/tomcat/webapps/ROOT.war
#ROOT.war is the tomca'ts default application

EXPOSE 8080 
CMD ["catalina.sh", "run"]
#tomcat is going to run the process on port 8080
#CMD["catalina.sh", "run"] to run the default tomcat server
#these things are based on tomcat documentation on docker hub