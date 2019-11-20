FROM frolvlad/alpine-glibc

RUN sed -i 's@dl-cdn.*alpinelinux.org@mirrors.ustc.edu.cn@g' /etc/apk/repositories
RUN apk update && apk add libaio

COPY instantclient-sqlplus-linux.x64-19.3.0.0.0dbru.zip /usr/local/1.zip
COPY instantclient-basiclite-linux.x64-19.3.0.0.0dbru.zip /usr/local/2.zip
RUN cd /usr/local && unzip 1.zip && unzip 2.zip && rm 1.zip 2.zip

ENV ORACLE_BASE /usr/local/instantclient_19_3
ENV LD_LIBRARY_PATH /usr/local/instantclient_19_3
ENV TNS_ADMIN /usr/local/instantclient_19_3
ENV ORACLE_HOME /usr/local/instantclient_19_3
ENV PATH /usr/local/instantclient_19_3:$PATH
