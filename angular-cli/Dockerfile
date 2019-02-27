FROM node:11-alpine as node-angular-cli

LABEL authors="Daniel Resnitzky"

RUN apk update \
  && apk add --update alpine-sdk \
  && apk del alpine-sdk \
  && rm -rf /tmp/* /var/cache/apk/* *.tar.gz ~/.npm \
  && npm cache verify \
  && sed -i -e "s/bin\/ash/bin\/sh/" /etc/passwd

RUN apk add git

RUN adduser angular -SD -h /app

WORKDIR /app

RUN npm install -g @angular/cli

USER angular

RUN git config --global user.email dcresnitzky@gmail.com \
    &&  git config --global user.name "Daniel Resnitzky"
