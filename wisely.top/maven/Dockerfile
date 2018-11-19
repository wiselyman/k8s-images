FROM java:8
MAINTAINER 285414629@qq.com

ARG MAVEN_VERSION=3.6.0
ARG USER_HOME_DIR="/root"

RUN wget --no-verbose -O /tmp/$MAVEN_NAME.zip https://raw.githubusercontent.com/wiselyman/k8s-images/master/static/apache-maven-${MAVEN_VERSION}.zip \
    && mkdir -p /usr/share/ \
    && unzip  /tmp/apache-maven-${MAVEN_VERSION}.zip -d /usr/share \
    && mv apache-maven-${MAVEN_VERSION} maven \
    && ln -s /usr/share/maven/bin/mvn /usr/local/bin \
    && rm -f /tmp/$MAVEN_NAME.zip

ENV MAVEN_HOME /usr/share/maven
ENV MAVEN_CONFIG "$USER_HOME_DIR/.m2"

CMD ["mvn"]