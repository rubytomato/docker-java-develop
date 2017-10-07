FROM centos:7

RUN yum update -y && yum install -y java-1.8.0-openjdk java-1.8.0-openjdk-devel && yum reinstall -y glibc-common && yum -y clean all

ENV LANG ja_JP.UTF-8
ENV LANGUAGE ja_JP:ja
ENV JAVA_HOME /usr/lib/jvm/java-1.8.0-openjdk

RUN localedef -f UTF-8 -i ja_JP ja_JP.UTF-8
RUN unlink /etc/localtime
RUN ln -s /usr/share/zoneinfo/Japan /etc/localtime

EXPOSE 9000
