ARG BASE_IMAGE=registry.red-soft.ru/ubi8/ubi

FROM $BASE_IMAGE
ARG JENKINS_WAR_URL=https://get.jenkins.io/war-stable/2.504.3/jenkins.war
WORKDIR /root
RUN dnf install -y curl vim telnet ca-certificates wget java-21-openjdk java-21-openjdk-devel
RUN mkdir /usr/share/jenkins/ && wget $JENKINS_WAR_URL -O /usr/share/jenkins/jenkins.war
RUN groupadd jenkins && \
    useradd -m -g jenkins jenkins
RUN mkdir /jenkins_home
RUN chown -R jenkins:jenkins /jenkins_home && chown -R jenkins:jenkins /usr/share/jenkins

USER jenkins
WORKDIR /jenkins_home
CMD JENKINS_HOME=/jenkins_home java -jar /usr/share/jenkins/jenkins.war --httpPort=$JENKINS_PORT