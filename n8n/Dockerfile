# Baseado na camada #4 que confirmou Alpine 3.22
FROM n8nio/n8n:2.14.2

USER root

# No Alpine usamos apk. Instalando Python para os novos nós de código
RUN apk add --update --no-cache \
    python3 \
    py3-pip \
    ca-certificates \
    && ln -sf python3 /usr/bin/python

USER node

# O entrypoint já está definido na camada #23, então só o CMD basta
CMD ["n8n"]