FROM centos:7

RUN yum -y update;\
    yum -y install which ;\
    yum -y install wget ;\
    yum -y install sudo ;\
    yum -y install unzip;\
    yum -y install openssl;\
    yum -y install nano;\
    yum -y install sleep;\
    yum -y install initscripts;\
    yum clean all;

    #yum -y install git;\
    #yum -y install svn;\
    #yum -y install git-svn;\


#OpenJDK Java 11
RUN curl -sO https://download.oracle.com/java/GA/jdk11/9/GPL/openjdk-11.0.2_linux-x64_bin.tar.gz ;\
    tar zxvf openjdk-11.0.2_linux-x64_bin.tar.gz ;\
    mv jdk-11.0.2 /usr/local/ ; \
    ln -s /usr/local/jdk-11.0.2/bin/java /usr/bin/java ; \
    rm /openjdk-11.0.2_linux-x64_bin.tar.gz; \
    rm /usr/local/jdk-11.0.2/lib/src.zip

ENV JAVA_HOME=/usr/local/jdk-11.0.2
ENV PATH=$PATH:$JAVA_HOME/bin

RUN curl -sL https://rpm.nodesource.com/setup_10.x | bash - ;\
    yum install -y nodejs; \
    yum clean all && sudo yum makecache fast


RUN yum -y install httpd httpd-tools mod_ssl;\
    yum clean all; \
    systemctl enable httpd; \
    echo "ServerName localhost" >> /etc/httpd/conf/httpd.conf

#for psql commands
#RUN yum -y install postgresql
