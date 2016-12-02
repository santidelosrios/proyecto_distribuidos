FROM evarga/jenkins-slave

RUN apt-get update
RUN apt-get install -y wget
RUN apt-get install -y python python-dev python-distribute
RUN wget https://bootstrap.pypa.io/get-pip.py
RUN python get-pip.py
RUN pip install virtualenv
EXPOSE 22
