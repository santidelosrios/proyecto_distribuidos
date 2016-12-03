FROM evarga/jenkins-slave
#UPDATE AND INSTALL REQUIRED PACKAGES
RUN apt-get update
RUN apt-get install -y wget
RUN apt-get install -y python python-dev python-distribute
RUN apt-get install -y git
#INSTALL PYTHON AND VIRTUALENV
RUN wget https://bootstrap.pypa.io/get-pip.py
RUN python get-pip.py
RUN pip install virtualenv
#SET THE FOLDERS AND FILE UP
WORKDIR /home/jenkins
RUN mkdir /home/jenkins/.virtualenvs
WORKDIR /home/jenkins/.virtualenvs
#CREATE THE TEST PROJECT WITH VIRTUALENV
RUN virtualenv testproject
RUN . testproject/bin/activate
#INSTALL REQURIED PACKAGES TO RUN THE TEST
RUN pip install xmlrunner
RUN pip install unittest2
RUN pip install pytest
RUN pip install pytest-cov
RUN pip install flask
EXPOSE 22
