FROM node:lts-alpine3.17 as build
WORKDIR /app

COPY package*.json ./
COPY . .
RUN npm install
RUN npm audit fix
RUN npm run build

FROM node:lts-alpine3.17 as run
WORKDIR /app

COPY --from=build /app/package.json ./package.json
COPY --from=build /app/build ./build
RUN npm install --production

EXPOSE 5173
CMD ["npm", "run", "start"]