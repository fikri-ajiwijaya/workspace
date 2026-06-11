FROM debian:sid

ARG username='dev'
RUN useradd "${username}" -ms '/bin/bash'

USER "${username}"

RUN sed -i '/PS1.*\\\$/s/\\\$/\\n\0/' "${HOME}/.bashrc"
