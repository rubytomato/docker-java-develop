FROM mysql:5.7.19

COPY ./conf/mysqld.cnf /etc/mysql/mysql.conf.d

COPY ./sql/1_schema.sql /docker-entrypoint-initdb.d
COPY ./sql/2_init_memo_data.sql /docker-entrypoint-initdb.d

RUN chmod 644 /etc/mysql/mysql.conf.d/mysqld.cnf

ENV TZ=Asia/Tokyo

