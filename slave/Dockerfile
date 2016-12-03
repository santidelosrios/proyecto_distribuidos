FROM evarga/jenkins-slave

RUN apt-get update
RUN apt-get install -y wget
RUN apt-get install -y python python-dev python-distribute
RUN apt-get install -y git
RUN wget https://bootstrap.pypa.io/get-pip.py
RUN python get-pip.py
RUN pip install virtualenv
#USER jenkins
WORKDIR /home/jenkins
RUN mkdir /home/jenkins/.virtualenvs
WORKDIR /home/jenkins/.virtualenvs
RUN virtualenv testproject
RUN . testproject/bin/activate
RUN pip install xmlrunner
RUN pip install unittest2
RUN pip install pytest
RUN pip install pytest-cov
RUN pip install flask
EXPOSE 22
