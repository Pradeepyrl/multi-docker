FROM node:14.14.0-alpine as builder

WORKDIR /app

COPY package.json .
RUN npm config set strict-ssl false
RUN npm set registry http://registry.npmjs.org/
RUN npm install --verbose
COPY . .
RUN npm run build

FROM nginx
EXPOSE 3000
COPY ./ngix/default.conf /etc/nginx/conf.d/default.conf
COPY --from=builder /app/build /usr/share/nginx/html