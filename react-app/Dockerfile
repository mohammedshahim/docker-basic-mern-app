# Use an official Node.js runtime as the base image
FROM node:14 as build-stage

# Set the working directory inside the container
WORKDIR /usr/src/app

# Copy package.json and package-lock.json to the working directory
COPY package*.json ./

# Install application dependencies
RUN npm install

# Copy the entire application directory to the working directory
COPY . .

# Build the React app for production
RUN npm run build

# Use a lightweight web server to serve the static files
FROM nginx:alpine

# Copy the production build files to the web server directory
COPY --from=build-stage /usr/src/app/build /usr/share/nginx/html

# Expose the default HTTP port
EXPOSE 80

# Start the web server
CMD ["nginx", "-g", "daemon off;"]
