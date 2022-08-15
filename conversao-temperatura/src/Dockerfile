FROM node:16-alpine AS builder

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . ./app

EXPOSE 8080
CMD [ "node", "server.js" ]

FROM nginx:alpine
COPY ./nginx.conf /etc/nginx/conf.d/app.conf
COPY --from=builder /app/build /app