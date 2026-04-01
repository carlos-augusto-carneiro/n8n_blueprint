# Baseado na versão estável 2.14.2
FROM n8nio/n8n:2.14.2

USER root

# Instala Python 3 e dependências para os novos Agentes de IA e Task Runners
RUN apk add --update --no-cache \
    python3 \
    py3-pip \
    ca-certificates \
    && ln -sf python3 /usr/bin/python

# Configuração dos Certificados (C6 Bank)
# Certifique-se de ter a pasta ./n8n/certs/ com seu arquivo .crt
COPY ./certs/c6_bank.crt /usr/local/share/ca-certificates/c6_bank.crt
RUN update-ca-certificates

# Retorna para o usuário node por segurança (Best Practice)
USER node

# O Render injeta a porta automaticamente, o n8n a lerá via ENV
CMD ["n8n"]