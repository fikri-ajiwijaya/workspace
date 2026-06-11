FROM debian:sid

RUN apt-get update && \
    apt-get -y install locales && \
    sed -i '/en_US.UTF-8/s/^# //g' '/etc/locale.gen' && \
    locale-gen

ENV LANG='en_US.UTF-8' LANGUAGE='en_US:en' LC_ALL='en_US.UTF-8'

ARG username='dev'
RUN useradd "${username}" -ms '/bin/bash'

USER "${username}"

RUN sed -i '/PS1.*\\\$/s/\\\$/\\n\0/' "${HOME}/.bashrc"
