# Stage 1
FROM node:20 as builder

WORKDIR /app

COPY . ./

RUN npm install 

# Stage 2
FROM node:20-slim as production

WORKDIR /app

COPY --from=builder /app ./

EXPOSE 4000

CMD ["npm", "run", "start"]
