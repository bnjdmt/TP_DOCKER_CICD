# Dockerfile node express
FROM node

WORKDIR /app

COPY package*.json .

RUN npm install

COPY . .

EXPOSE 9000:3000

CMD ["node","app.js"]