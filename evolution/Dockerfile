FROM evoapicloud/evolution-api:v2.3.6

USER root

# Instala as dependências de sistema (como ffmpeg)
RUN apk add --update --no-cache ffmpeg

# Dá permissão total para a pasta do prisma E para a pasta node_modules
# Isso permite que o 'npx prisma generate' reescreva o cliente do banco sem ser bloqueado
RUN mkdir -p ./prisma/migrations && \
    chown -R node:node ./prisma ./node_modules && \
    chmod -R 777 ./prisma ./node_modules

USER node