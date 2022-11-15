ARG BASE_IMAGE_NAME=debian
ARG BASE_IMAGE_TAG=stretch-20220125-slim

FROM ${BASE_IMAGE_NAME}:${BASE_IMAGE_TAG}

COPY rekinit.sh /rekinit.sh

RUN apt -qq update && \
	    apt -qq install -y \
        krb5-user && \
        mkdir /krb5 && chmod 755 /krb5 

VOLUME ["/krb5","/dev/shm","/etc/krb5.conf.d"]

ENTRYPOINT ["/rekinit.sh"]