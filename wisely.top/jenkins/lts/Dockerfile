FROM jenkins/jenkins:lts
MAINTAINER 285414629@qq.com
ARG DOCKER_VERSION=17.06.2~ce-0~debian

USER root

ENV MAVEN_NAME apache-maven-3.6.0

RUN apt-get update && \
    apt-get install -qq -y --no-install-recommends \
      apt-transport-https \
      ca-certificates \
      curl \
      gnupg2 \
      software-properties-common && \
    curl -fsSL https://download.docker.com/linux/debian/gpg | apt-key add - && \
    apt-key fingerprint 0EBFCD88 && \
    add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/debian stretch stable" && \
    add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/debian stretch stable" && \
    apt-get update && \
    apt-get install -qq -y --no-install-recommends docker-ce=${DOCKER_VERSION} && \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*



RUN wget --no-verbose -O /tmp/$MAVEN_NAME.zip https://raw.githubusercontent.com/wiselyman/k8s-images/master/static/${MAVEN_NAME}.zip \
    && mkdir /opt/maven \
    && unzip  /tmp/$MAVEN_NAME.zip -d /opt/maven \
    && ln -s /opt/maven/bin/mvn /usr/local/bin \
    && rm -f /tmp/$MAVEN_NAME.zip

USER jenkins