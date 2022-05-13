FROM node:14 AS builder
RUN apt-get update && apt-get install -y  git
WORKDIR /usr/app
RUN git clone https://github.com/MTA1711/tasks-client-angular.git ./ &&  npm install && npm run build --prod

FROM nginx:stable-alpine
COPY --from=builder /usr/app/dist /usr/share/nginx/html
