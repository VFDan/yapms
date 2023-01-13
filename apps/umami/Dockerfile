FROM node:19-alpine

ENV DATABASE_URL mysql://username:mypassword@localhost:3306/mydb

RUN apk add --no-cache \
    git \
    ca-certificates

RUN git clone https://github.com/umami-software/umami.git

RUN npm install -g yarn

RUN cd umami

RUN yarn install

RUN yarn build

RUN yarn update-db

CMD ["yarn", "start"]