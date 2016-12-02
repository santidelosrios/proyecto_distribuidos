FROM jenkins

#install plugins 
RUN usr/local/bin/install-plugins.sh github:1.22.3
RUN /usr/local/bin/install-plugins.sh docker:0.16.2
RUN /usr/local/bin/install-plugins.sh saferestart:0.3
#disable security
ENV JAVA_OPTS="-Djenkins.install.runSetupWizard=false"
#copy the jar to access de jenkins cli
#COPY jenkins-cli.jar .
#expose the port needed to access via web
EXPOSE 8080
