FROM node:18-alpine3.15
ENV NODE_VERSION 16.15.0

WORKDIR /src/

RUN apk update && \
    npm install -g npm && \
    npm install -g @vue/cli

COPY ["package*.json", "./"]
RUN npm ci
COPY [".", "./"]

RUN  npm run build
CMD ["npm", "run", "serve"]