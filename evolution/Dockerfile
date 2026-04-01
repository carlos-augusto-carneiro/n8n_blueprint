# Utilizando a build v2.3.6
FROM evoapicloud/evolution-api:v2.3.6

USER root

# No Alpine, usamos 'apk' em vez de 'apt-get'
RUN apk add --update --no-cache \
    ffmpeg

USER node

EXPOSE 8080

CMD ["node", "./dist/src/main.js"]