FROM jenkins/jenkins:lts
# if we want to install via apt
USER root
RUN apt-get update
RUN apt-get install -y apt-transport-https ca-certificates curl gnupg-agent software-properties-common git awscli
RUN curl -fsSL https://download.docker.com/linux/ubuntu/gpg | apt-key add -
# XXX bionic ma byt vysledok z prikazu :
#       lsb_release -cs
RUN add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable"
RUN apt-get update
RUN apt-get install -y docker-ce-cli
RUN addgroup --gid 999 docker
RUN adduser jenkins docker
# drop back to the regular jenkins user - good practice
USER jenkins
