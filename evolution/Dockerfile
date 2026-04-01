# Utilizando a build 2.14.2 estável
FROM evoapicloud/evolution-api:v2.14.2

USER root

# Instala ffmpeg para conversão de mídias e áudios
RUN apt-get update && apt-get install -y \
    ffmpeg \
    && rm -rf /var/lib/apt/lists/*

USER node

# Porta padrão da API
EXPOSE 8080

# Comando de inicialização padrão da Evolution v2
CMD ["node", "./dist/src/main.js"]