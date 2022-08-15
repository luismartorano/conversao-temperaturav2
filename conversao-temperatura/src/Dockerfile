FROM node:16-alpine AS builder

WORKDIR /app
COPY . /app
RUN npm ci
RUN npm run build


FROM nginx:alpine
COPY ./nginx.conf /etc/nginx/conf.d/app.conf
COPY --from=builder /app/build /app