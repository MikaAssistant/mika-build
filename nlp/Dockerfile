FROM node:8.11.1

# Maintainer
MAINTAINER Diogo Bemfica "diogo.fragabemfica@gmail.com"

RUN apt-get update && apt-get clean
RUN npm i pm2 -g --silent

# BUILD
WORKDIR /home/node
RUN git clone https://github.com/MikaAssistant/mika-nlp.git app
WORKDIR /home/node/app
ADD ./.env /home/node/app/.env
RUN npm install --silent
ENV NODE_ENV=production

CMD [ "pm2-docker", "app.js" ]
