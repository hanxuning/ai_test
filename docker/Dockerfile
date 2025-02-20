FROM centos
RUN /bin/sh -c yum -y install vim
ADD jdk-8u181-linux-x64.tar.gz /usr/local/
ADD apache-tomcat-8.5.79.tar.gz /usr/local/tomcat
COPY readme.txt  /usr/local/readme.txt
ENV MYPATH /usr/local
WORKDIR $MYPATH
ENV JAVA_HOME /usr/local/jdk-8u181
ENV CLASSPATH $JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar
ENV CATALINA_HOME /usr/local/apache-tomcat-8.5.79
ENV CATALINA_BASH /usr/local/apache-tomcat-8.5.79
ENV PATH $PATH:$JAVA_HOME/bin:$ CATALINA_HOME/lib:CATALINA_HOME/bin

EXPOSE 8080

CMD /usr/local/apache-tomcat-8.5.79/bin/startup.sh && tail -F /usr/local/apache-tomcat-8.5.79/bin/logs/catalina.out

