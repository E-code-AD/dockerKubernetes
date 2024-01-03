FROM node:19.6-alpine

ENV NODE_ENV production

WORKDIR /usr/src/app

COPY package*.json .

RUN --mount=type=cache,target=/usr/src/app/.npm \
    npm set cache /usr/src/app/.npm && \
    npm ci

USER node

COPY --chown=node:node . .

EXPOSE 3000

CMD ["node", "index.mjs"]