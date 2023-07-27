# Use the official Node.js image as the base image
FROM node:14

# Set the working directory inside the container
WORKDIR /app

# Copy the package.json and package-lock.json files to the working directory
COPY package.json package-lock.json ./

# Install dependencies
RUN npm install --legacy-peer-deps


RUN npm install

# Copy the rest of the frontend project files to the working directory in the container
COPY . .

# Build the frontend application
RUN npm run build

# Expose the port on which the frontend will run (assuming it's 3000, update if needed)
EXPOSE 3000

# Command to run the frontend application
CMD ["npm", "start"]

