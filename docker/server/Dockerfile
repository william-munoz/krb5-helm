ARG BASE_IMAGE_NAME=debian
ARG BASE_IMAGE_TAG=stretch-20220125-slim

FROM ${BASE_IMAGE_NAME}:${BASE_IMAGE_TAG}

COPY init_db.sh /init_db

RUN apt -qq update && \
	    apt -qq install -y \
        cracklib-runtime \
        libcrack2 \
        expect \
        krb5-user \
        krb5-pkinit \
        krb5-auth-dialog \
        krb5-admin-server \
        krb5-kdc \
        krb5-kdc-ldap \
        krb5-config \
        libkrb5-3 \
        libpam-krb5 \
        openjdk-8-jre-headless \
        openssh-server \
        openssh-client \
        less \
    && chmod a+x /init_db \
    && /usr/bin/ssh-keygen -A \
    && useradd iguazio \
    && useradd krbtest \
    && mkdir /tmp/ccache \
    && mkdir /run/sshd \
    && chmod 755 /run/sshd \
    && chown root:root /run/sshd