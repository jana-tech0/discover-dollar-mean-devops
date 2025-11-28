FROM node:18-alpine

WORKDIR /app

# Copy package files
COPY package*.json ./

# Install dependencies including Angular CLI
RUN npm install -g @angular/cli@15
RUN npm install

# Copy source code
COPY . .

# Expose Angular dev server port
EXPOSE 4200

# Start Angular dev server (matches your command)
CMD ["ng", "serve", "--host", "0.0.0.0", "--port", "4200", "--disable-host-check"]