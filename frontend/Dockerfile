# Use an official Node.js runtime as the base image
FROM node:12

# Set the working directory
WORKDIR /app

# Copy package.json and package-lock.json
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application code
COPY . .

# Expose Vite's default port
EXPOSE 8080

# Start the Vite development server
CMD ["npm", "run", "dev", "--", "--host", "--port", "8080"]