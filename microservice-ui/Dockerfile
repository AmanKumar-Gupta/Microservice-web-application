# Use Node.js image
FROM node:12.13.1

WORKDIR /app

# Copy project files into the container
COPY . .

# Install dependencies
RUN npm install

# Expose the port the app runs on
EXPOSE 3000

# Start the application
CMD ["npm", "start"]