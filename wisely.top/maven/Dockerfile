FROM java:8
MAINTAINER 285414629@qq.com

ARG MAVEN_VERSION=3.6.0
ARG USER_HOME_DIR="/root"

RUN wget --no-verbose -O /tmp/maven.zip https://raw.githubusercontent.com/wiselyman/k8s-images/master/static/apache-maven-${MAVEN_VERSION}.zip \
    && mkdir -p /usr/share/ \
    && unzip  /tmp/maven.zip -d /usr/share \
    && ln -s /usr/share/maven/bin/mvn /usr/local/bin \
    && rm -f /tmp/maven.zip

ENV MAVEN_HOME /usr/share/maven
ENV MAVEN_CONFIG "$USER_HOME_DIR/.m2"

CMD ["mvn"]