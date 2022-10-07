FROM node:alpine as node

WORKDIR /src
COPY . .

RUN npm install && npm run build

FROM nginx:1.23.1-alpine
COPY nginx.conf /etc/nginx/nginx.conf
COPY --from=node /src/dist /usr/share/nginx/html/movies
