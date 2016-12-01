FROM jenkins

#copy de plugins.txt file
COPY plugins.txt /usr/share/jenkins/plugins.txt
#install plugins 
RUN /usr/local/bin/plugins.sh /usr/share/jenkins/plugins.txt
#expose the port needed to acces via web
EXPOSE 8080
