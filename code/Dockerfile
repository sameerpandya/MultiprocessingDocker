FROM python:3.7-buster

RUN pip install pika

ARG UID=2000
ARG GID=2000

RUN groupadd -g ${GID} multi || groupmod -n multi `getent group ${GID} | cut -d: -f1` \
    && useradd --shell /bin/bash -u ${UID} -g ${GID} -m multi 

ADD ./scripts /home/multi/scripts

ENTRYPOINT ["tail", "-f", "/dev/null"]