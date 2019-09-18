FROM node:alpine as builder
WORKDIR '/app'
COPY package.json .
RUN npm i
COPY . .
CMD [ "npm", "run", "start" ]

FROM nginx
EXPOSE 3000
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
COPY --from=builder /app/builder /usr/share/nginx/html