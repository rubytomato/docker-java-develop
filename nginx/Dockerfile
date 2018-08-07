FROM centos:7

COPY ./repo/nginx.repo /etc/yum.repos.d

RUN yum update -y && \
    yum install -y --enablerepo=nginx nginx && \
    yum reinstall -y glibc-common && \
    yum -y clean all

ENV LANG ja_JP.UTF-8
ENV LANGUAGE ja_JP:ja

RUN localedef -i ja_JP -c -f UTF-8 ja_JP.UTF-8 && \
    unlink /etc/localtime && \
    ln -s /usr/share/zoneinfo/Japan /etc/localtime

COPY ./conf/default.conf /etc/nginx/conf.d

RUN chmod 664 /etc/nginx/conf.d/default.conf

RUN ln -sf /dev/stdout /var/log/nginx/access.log && \
    ln -sf /dev/stderr /var/log/nginx/error.log

EXPOSE 80

STOPSIGNAL SIGTERM

CMD ["nginx", "-g", "daemon off;"]
