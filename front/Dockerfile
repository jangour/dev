# Use an official Node.js runtime as a parent image
FROM node:14

# Set the working directory in the container
WORKDIR /app

# Copy the Angular app files into the container
COPY . .

# Install Angular CLI (if needed)
RUN npm install -g @angular/cli

# Build the Angular app
RUN ng build --prod

# Expose the port your app will run on (if applicable)
EXPOSE 80

# Define the command to start your Angular app
CMD ["nginx", "-g", "daemon off;"]
