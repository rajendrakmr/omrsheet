# Stage 1: Build the React app
FROM node:20 as builder

WORKDIR /app 

COPY . ./
RUN npm install 
COPY . .
 
FROM node:20-slim as production

WORKDIR /app
 
COPY --from=builder /app ./
 
EXPOSE 3000

# Run application
CMD ["npm","run","start", "3000"]
