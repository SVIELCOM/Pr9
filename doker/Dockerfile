#FROM alpine:3.15
#RUN apk add --no-cache python3 py3-pip && pip3 install --upgrade pip && pip3 install flask && pip3 install configparser
#ENTRYPOINT [ "/bin/sh" ]
#75.2MB


#FROM python:3.9-slim 
#RUN pip3 install --no-cache-dir flask configparser psycopg2-binary
#ENTRYPOINT [ "/bin/sh" ]
#140MB

#FROM ubuntu:18.04
#RUN apt-get update && apt-get install --yes python3 python3-psycopg2 python3-flask python3-pip && pip3 install --no-cache-dir configparser && apt-get --yes purge python3-pip && apt-get clean
#491MB

FROM python:3.9-alpine
RUN apk update --no-cache && \
    apk add build-base postgresql-dev libpq --no-cache --virtual .build-deps && \
    pip3 install --upgrade --no-cache-dir psycopg2-binary flask configparser && \
    apk del .build-deps
RUN apk add postgresql-libs libpq --no-cache
ENTRYPOINT [ "/bin/sh" ]
EXPOSE 80