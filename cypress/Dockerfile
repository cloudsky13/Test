# Use an official Node.js runtime as a parent image
FROM node:14-slim
# Set the working directory to /app
WORKDIR /app
# Copy package.json and package-lock.json to the working directory
COPY package*.json ./
# Install Cypress dependencies
RUN apt-get update && \
    apt-get install -y libgtk2.0-0 libgtk-3-0 libgbm-dev libnotify-dev libgconf-2-4 libnss3 libxss1 libasound2 libxtst6 xauth xvfb && \
    npm install
# Copy the rest of the application code to the working directory
COPY . .
# Run Cypress tests
CMD ["npm", "run", "cypress:run"]

