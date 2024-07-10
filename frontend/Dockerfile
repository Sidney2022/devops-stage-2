# # Use the official Node.js image
# FROM node:14 as build

# # Set working directory
# WORKDIR /app

# # Install dependencies
# COPY frontend/package*.json ./
# RUN npm install

# # Copy app source
# COPY frontend ./

# # Build app
# RUN npm run build

# # Production environment
# FROM nginx:alpine
# COPY --from=build /app/build /usr/share/nginx/html
# EXPOSE 80
# CMD ["nginx", "-g", "daemon off;"]


# Use an official node image as the base image
FROM node:14

# Set the working directory
WORKDIR /app

# Copy package.json and package-lock.json to the working directory
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application source code to the working directory
COPY . .

# Build the application
RUN npm run build

# Production environment
FROM nginx:alpine
COPY --from=build /app/build /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
