FROM node:14-alpine

RUN apk update 
RUN apk upgrade 

RUN apk add --no-cache build-base vim curl git mysql-client gawk python3 g++ make bash libbz2
RUN npm i -g nodemon

ARG NODE_ENV=development
ENV NODE_ENV=${NODE_ENV}
ENV NODE_PORT=4848

RUN mkdir /api
WORKDIR /api

COPY package*.json ./
RUN npm install
ADD . ./

EXPOSE 4848
CMD npm run start