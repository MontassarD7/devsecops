# Use official Node.js LTS image
FROM node:18

# Create app directory
WORKDIR /usr/src/app

# Copy package.json and package-lock.json
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the app source code
COPY . .

# Expose port the app runs on
EXPOSE 8080

# Install Perl and Nikto
RUN apt-get update && \
    apt-get install -y nikto && \
    rm -rf /var/lib/apt/lists/*

# Start the app
CMD ["node", "index.js"]
