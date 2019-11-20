FROM frolvlad/alpine-glibc

RUN apk update && apk add libaio

COPY instantclient-sqlplus-linux.x64-12.2.0.1.0.zip /usr/local/1.zip
COPY instantclient-basiclite-linux.x64-12.2.0.1.0.zip /usr/local/2.zip
RUN cd /usr/local && unzip 1.zip && unzip 2.zip && rm 1.zip 2.zip

ENV ORACLE_BASE /usr/local/instantclient_12_2
ENV LD_LIBRARY_PATH /usr/local/instantclient_12_2
ENV TNS_ADMIN /usr/local/instantclient_12_2
ENV ORACLE_HOME /usr/local/instantclient_12_2
ENV PATH /usr/local/instantclient_12_2:$PATH
