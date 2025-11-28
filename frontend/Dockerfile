FROM node:18-alpine AS build

WORKDIR /app

# Copy package files
COPY package*.json ./

# Install dependencies including Angular CLI
RUN npm install -g @angular/cli@15
RUN npm install

# Copy source code
COPY . .

# Build the Angular app for production
RUN ng build --configuration=production

# Production stage
FROM nginx:alpine

# Copy built app from build stage - FIXED PATH
COPY --from=build /app/dist/ /usr/share/nginx/html

# Copy nginx configuration
COPY nginx.conf /etc/nginx/conf.d/default.conf

# Expose port 80
EXPOSE 80

# Start nginx
CMD ["nginx", "-g", "daemon off;"]
