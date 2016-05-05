FROM node:6.0-onbuild
# replace this with different ver. of nodeJS if needed e.g. 4.4-onbuild

RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

ONBUILD COPY package.json /usr/src/app/
ONBUILD RUN npm install
RUN npm install forever -g
RUN npm install babel -g
RUN npm install babel-preset-es2015 -g
#RUN npm uninstall sails -g
#RUN npm install git://github.com/balderdashy/sails.git#master -g
ONBUILD COPY . /usr/src/app

#COPY irc-slack-config.json /usr/src/app/irc-slack-config.json

#RUN cd /usr/src/app/ && npm install
#EXPOSE 80

CMD ["node", "/usr/src/app/index.js", "--config", "/usr/src/app/irc-slack-config.json"]
#CMD ["node", "/usr/src/app/lib/index.js", "--config", "/usr/src/app/irc-slack-config.json"]
