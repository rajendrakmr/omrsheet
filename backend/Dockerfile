#stage 1
FROM node:20 as builder

WORKDIR /app

COPY . .

RUN npm intall

RUN npm run build 

#stage 2
FROM node:20-slim as production

WORKDIR /app

COPY --from=builder /app ./app

EXPOSE 4000

CMD ["npm", "run"]
