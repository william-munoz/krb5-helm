ARG BASE_IMAGE_NAME=debian
ARG BASE_IMAGE_TAG=stretch-20220125-slim

FROM ${BASE_IMAGE_NAME}:${BASE_IMAGE_TAG}

COPY init_db.sh /init_db

RUN apt-get install -y \
        cracklib-runtime \
        libcrack2 \
        expect \
        krb5-user \
        krb5-pkinit \
        krb5-auth-dialog \
        krb5-admin-server \
        krb5-kdc \
        krb5-kdc-ldap \
        libkrb5-3 \
        openjdk-8-jre-headless \
        pam_krb5 \
        openssh-server \
        openssh-client \
        less \
    && chmod a+x /init_db \
    && /usr/bin/ssh-keygen -A \
    && useradd iguazio \
    && useradd krbtest \
    && mkdir /tmp/ccache