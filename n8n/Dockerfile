FROM n8nio/n8n:2.14.2

USER root

# Como a imagem é baseada em Debian, usamos apt-get em vez de apk.
# Instalando Python para os novos nós de código:
RUN apt-get update && apt-get install -y \
    python3 \
    python3-pip \
    ca-certificates \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* \
    && ln -sf /usr/bin/python3 /usr/bin/python

USER node

# O entrypoint já está definido na imagem base, então só o CMD basta
CMD ["n8n"]