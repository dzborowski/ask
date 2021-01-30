FROM node:12.20.0-alpine3.11 AS client_build

WORKDIR /home/node/app

COPY package*.json ./

RUN ["npm", "ci"]

COPY . .

RUN ["npm", "run", "build"]

FROM nginx:1.19.5

COPY --from=client_build /home/node/app/nginx.conf /etc/nginx/nginx.conf
COPY --from=client_build /home/node/app/build/ /usr/share/nginx/html/
