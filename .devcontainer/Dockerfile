FROM debian:sid

RUN apt-get update && \
    apt-get -y install locales && \
    sed -i '/en_US.UTF-8/s/^# //g' '/etc/locale.gen' && \
    locale-gen

ENV LANG='en_US.UTF-8' LANGUAGE='en_US:en' LC_ALL='en_US.UTF-8'

RUN apt-get -y dist-upgrade && \
    apt-get -y autopurge && \
    apt-get -y install curl git gnupg less man parallel patch ssh vim wget xz-utils

ARG username='dev'
RUN useradd "${username}" -ms '/bin/bash'

USER "${username}"

COPY --chmod=644 --chown="${username}:${username}" '.vimrc' '/tmp'
RUN sed -i '/PS1.*\\\$/s/\\\$/\\n\0/' "${HOME}/.bashrc" && \
    mv '/tmp/.vimrc' "${HOME}"
