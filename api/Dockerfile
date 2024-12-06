# Use Node.js as the base image
FROM node:16-alpine

WORKDIR /app/api

# Install build dependencies
RUN apk add --no-cache python3 make g++ git

# Copy package files
COPY api/package*.json api/yarn.lock ./

# Install dependencies
RUN yarn install

# Copy API source code
COPY api/ .

# Create uploads directory and set permissions
RUN mkdir -p public/uploads && chmod 777 public/uploads

# Build the application
RUN yarn build

EXPOSE 1337

# Start command that works with both development and production
CMD ["sh", "-c", "yarn seed && yarn develop"]