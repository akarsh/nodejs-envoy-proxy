# Use an official Node.js runtime as the base image
FROM node:21.6.1-alpine

# Set the working directory in the container
WORKDIR /usr/src/app

# Copy package.json and package-lock.json to the working directory
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of your application code to the working directory
COPY . .

# Expose the port on which your Node.js server listens
EXPOSE 3000

# Command to start your Node.js server
CMD ["npm", "start"]
