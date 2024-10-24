FROM node:20-alpine

RUN apk update
RUN apk upgrade

WORKDIR /home/node

# Install tileserver-gl-light
RUN npm install -g http-server
RUN http-server --help

COPY style.json .
COPY fonts/ fonts/
COPY sprites/ sprites/

EXPOSE 8888

CMD ["http-server", "--cors", "-p", "8888"]