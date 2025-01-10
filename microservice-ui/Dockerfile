FROM node:12.13.1 as builder

WORKDIR /app

COPY . .

RUN npm install

RUN npm run-script build
# Use an Nginx image to serve the built files
FROM nginx:alpine

# # Copy the built files into the Nginx container
COPY --from=builder /app/dist/microservice-ui /usr/share/nginx/html

EXPOSE 80
