# Use an official Node.js runtime as the base image
FROM node:14

# Set the working directory inside the container
WORKDIR /usr/src/app

# Copy package.json and package-lock.json to the working directory
COPY package*.json ./

# Install application dependencies
RUN npm install

# Copy the entire application directory to the working directory
COPY . .

# Expose the port that your Express.js application listens on
EXPOSE 3000

# Start the application
CMD [ "npm", "start" ]
