FROM node:latest

ENV \
    LANG=C.UTF-8 \
    LC_ALL=C.UTF-8

RUN \
    adduser \
        --disabled-password \
        --group \
        --home /var/lib/imagehosterd \
        --shell /bin/bash \
        --system \
        imagehosterd

USER imagehosterd

ENV HOME=/var/lib/imagehosterd

WORKDIR ${HOME}

COPY \
    --chown=imagehosterd:imagehosterd \
    . \
    .

RUN NODE_ENV=development npm install

EXPOSE ${PORT}

ENTRYPOINT ["npm", "run", "start"]
