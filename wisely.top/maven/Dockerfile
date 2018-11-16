FROM java:8
MAINTAINER 285414629@qq.com
ENV MAVEN_NAME apache-maven-3.6.0
RUN wget --no-verbose -O /tmp/$MAVEN_NAME.zip https://raw.githubusercontent.com/wiselyman/k8s-images/master/static/${MAVEN_NAME}.zip \
    && mkdir /opt/maven \
    && unzip  /tmp/$MAVEN_NAME.zip -d /opt/maven \
    && ln -s /opt/maven/bin/mvn /usr/local/bin \
    && rm -f /tmp/$MAVEN_NAME.zip
