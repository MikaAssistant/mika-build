FROM node:8.11.1

# Maintainer
MAINTAINER Diogo Bemfica "diogo.fragabemfica@gmail.com"

RUN apt-get update && apt-get clean
RUN npm i pm2 -g --silent

# BUILD
WORKDIR /home/node
RUN git clone -b 0.2.0 https://github.com/MikaAssistant/mika-kernel.git app
WORKDIR /home/node/app
RUN npm install --silent
ADD ./.env /home/node/app/.env
ENV NODE_ENV=production

EXPOSE 1982
EXPOSE 43210

CMD [ "pm2-docker", "app.js" ]
