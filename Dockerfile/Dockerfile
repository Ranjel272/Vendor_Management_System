# Use an official Node.js runtime as a parent image
FROM node:16

# Set the working directory inside the container
WORKDIR /app

# Copy package.json and package-lock.json
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application code
COPY . .

# Build the app for production
RUN npm run build

# Set the environment to production
ENV NODE_ENV=production

# Expose port 3000
EXPOSE 3000

# Serve the app using a lightweight server like serve
CMD ["npx", "serve", "build"]
