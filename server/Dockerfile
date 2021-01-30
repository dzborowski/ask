FROM node:12.20.0-alpine3.11

USER node:node

RUN mkdir -p /home/node/app/node_modules && chown -R node:node /home/node/app

WORKDIR /home/node/app

COPY --chown=node:node package*.json ./

RUN ["npm", "ci"]

COPY --chown=node:node . .

EXPOSE ${PORT}

CMD ["npm", "start"]
