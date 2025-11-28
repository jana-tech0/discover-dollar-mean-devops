FROM node:18-alpine

WORKDIR /app

# Copy package files
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy source code
COPY . .

# Expose port (matches your server.js port)
EXPOSE 8080

# Start the server (matches your command)
CMD ["node", "server.js"]