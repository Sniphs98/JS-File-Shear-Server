FROM node:lts-alpine3.17
WORKDIR /app
COPY app.js ./
COPY package*.json ./
COPY views ./views/
RUN npm install -g npm@9.4.2
RUN npm install
EXPOSE 3000
CMD ["npm", "start"]