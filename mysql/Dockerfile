FROM mysql:8.0.11

COPY ./conf/mysqld.cnf /etc/mysql/conf.d

COPY ./sql/1_schema.sql /docker-entrypoint-initdb.d
COPY ./sql/2_init_memo_data.sql /docker-entrypoint-initdb.d

RUN chmod 664 /etc/mysql/conf.d/mysqld.cnf
# RUN mkdir -p /var/log/mysql && chown mysql:mysql /var/log/mysql && chmod 664 /var/log/mysql

ENV TZ=Asia/Tokyo
