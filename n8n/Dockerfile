FROM n8nio/n8n:stable

# É obrigatório mudar para root para instalar pacotes no Debian
USER root

# No Debian, usamos apt-get em vez de apk
RUN apt-get update && apt-get install -y \
    python3 \
    python3-pip \
    ca-certificates \
    && ln -sf /usr/bin/python3 /usr/bin/python \
    && rm -rf /var/lib/apt/lists/*

# Volta para o usuário padrão para rodar o n8n com segurança
USER node

CMD ["n8n"]