FROM evoapicloud/evolution-api:v2.3.6

USER root

RUN apk add --update --no-cache ffmpeg

RUN mkdir -p ./prisma/migrations ./instances && \
    chown -R node:node ./prisma ./node_modules ./instances && \
    chmod -R 777 ./prisma ./node_modules ./instances

USER node