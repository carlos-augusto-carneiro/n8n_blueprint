FROM evoapicloud/evolution-api:v2.3.6

USER root

# Instala as dependências de sistema (como ffmpeg)
RUN apk add --update --no-cache ffmpeg

# Dá permissão total para a pasta do prisma, permitindo as migrações do banco
RUN mkdir -p ./prisma/migrations && chown -R node:node ./prisma && chmod -R 777 ./prisma

USER node

# A imagem original já possui o CMD e ENTRYPOINT corretos, não precisamos repeti-los