# Stage 1: Build the React app
FROM node:20 as builder

WORKDIR /app

# Install dependencies
COPY package.json package-lock.json ./
RUN npm install

# Copy the source code and build the React app
COPY . .
RUN npm run build

# Stage 2: Serve the React app with Node.js
FROM node:20-slim as production

WORKDIR /app

# Copy only the build artifacts from the builder stage
COPY --from=builder /app/build ./build

# Install a lightweight HTTP server globally
RUN npm install -g serve

# Expose the port the app will run on
EXPOSE 3000

# Default command to serve the app
CMD ["serve", "-s", "build", "-l", "3000"]
