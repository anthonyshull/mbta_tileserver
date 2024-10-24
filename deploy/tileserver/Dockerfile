FROM node:20-alpine

RUN apk update
RUN apk upgrade

WORKDIR /home/node

# Install tileserver-gl-light
RUN npm install -g tileserver-gl-light
RUN tileserver-gl-light --help

COPY config.json .
COPY style.json .
COPY data/ data/

EXPOSE 9999

CMD ["tileserver-gl-light", "-p", "9999", "-c", "config.json"]