# Use an official Node.js runtime as a parent image
FROM node:16

# Set the working directory inside the container
WORKDIR /app

# Copy package.json and package-lock.json (if present) for installing dependencies
COPY package*.json ./

# Install dependencies (use npm ci for a clean install based on package-lock.json)
RUN npm ci

# Copy the rest of the application code into the container
COPY . .

# Build the app for production (this step may be unnecessary if you don't need to build it)
RUN npm run build

# Set the environment to production
ENV NODE_ENV=production

# Expose port 3000
EXPOSE 3000

# Serve the app using a lightweight server like 'serve'
CMD ["npx", "serve", "build"]
