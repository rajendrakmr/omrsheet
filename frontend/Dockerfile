#stage 1
FROM node:20 as builder

WORKDIR /app

COPY . .

RUN npm intall

RUN npm run build 

#stage 2
FROM nginx:stable-alpine as production

WORKDIR /usr/share/nginx/html

COPY --from=builder /app/build ./

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]




