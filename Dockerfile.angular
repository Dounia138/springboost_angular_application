FROM node:18-buster

ADD . /app
WORKDIR /app

RUN npm i --force

RUN npm run build
RUN npm install serve -g

CMD ["serve", "-s", "dist/browser", "-l", "4200"]