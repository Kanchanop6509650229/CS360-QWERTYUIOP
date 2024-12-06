# Use Node.js as the base image
FROM node:16-alpine

WORKDIR /app/client

# Copy package files  
COPY client/package*.json client/yarn.lock ./

# Install dependencies
RUN yarn install

# Copy client source code
COPY client/ .

# Build the application
RUN yarn build

EXPOSE 3000

# Use a CMD instead of direct command to allow override in docker run
CMD ["yarn", "dev"]