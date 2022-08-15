FROM node:14

WORKDIR /usr/src/app

COPY package*.json ./

RUN npm install

COPY . .

EXPOSE 80
CMD [ "node", "server.js" ]

FROM nginx:alpine
COPY ./nginx.conf /etc/nginx/conf.d/app.conf
COPY --from=builder . /app