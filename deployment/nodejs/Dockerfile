FROM node:alpine
MAINTAINER juliuscanute@touchcapture.net
RUN apk update
RUN apk add --virtual build-deps npm git openssh
RUN mkdir /usr/share/website
WORKDIR /usr/share/website
RUN git clone https://github.com/juliuscanute/node-mysql-crud-app.git
RUN npm install node-mysql-crud-app
RUN rm -rf node-mysql-crud-app/.git
RUN apk --purge -v del build-deps
RUN rm /var/cache/apk/*
RUN rm -rf node-mysql-crud-app/deployment/*
EXPOSE 2000/tcp
ENTRYPOINT ["node","node-mysql-crud-app/app.js"]
