FROM node:14.14.0-alpine

WORKDIR /app

COPY package.json .
# RUN npm i -g npm@latest --verbose
RUN npm config set strict-ssl false
RUN npm set registry http://registry.npmjs.org/
RUN npm install --verbose

COPY . .

CMD ["npm", "run", "start"]