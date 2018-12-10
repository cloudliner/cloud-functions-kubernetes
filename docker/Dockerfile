FROM node

WORKDIR /hello-kubernetes

COPY package.json .
COPY package-lock.json .
COPY tsconfig.json .
COPY src/index.ts src/

RUN npm install
RUN npm run tsc

CMD node dist/index.js