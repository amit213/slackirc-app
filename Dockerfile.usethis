FROM node:5.11-onbuild
# replace this with different ver. of nodeJS if needed e.g. 4.4-onbuild

RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

ONBUILD COPY package.json /usr/src/app/
ONBUILD RUN npm install
RUN npm install forever -g
RUN npm install babel -g
RUN npm install babel-preset-es2015 -g
ONBUILD COPY . /usr/src/app

#EXPOSE 80

CMD ["node", "/usr/src/app/index.js", "--config", "/usr/src/app/irc-slack-config.json"]
#CMD ["node", "/usr/src/app/lib/index.js", "--config", "/usr/src/app/irc-slack-config.json"]
