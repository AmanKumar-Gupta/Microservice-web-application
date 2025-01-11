FROM node:12.13.1 as builder

WORKDIR /app

COPY . .

RUN npm install

EXPOSE 4200

CMD ["npm", "start"]
