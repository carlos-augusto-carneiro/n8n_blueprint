FROM n8nio/n8n:2.14.2

USER root

# 1. Recupera o instalador estático do apk nativamente, sem forçar repositórios de outras versões
RUN ARCH=$(uname -m) && \
    wget -qO- "http://dl-cdn.alpinelinux.org/alpine/latest-stable/main/${ARCH}/" | \
    grep -o 'href="apk-tools-static-[^"]*\.apk"' | head -1 | cut -d'"' -f2 | \
    xargs -I {} wget -q "http://dl-cdn.alpinelinux.org/alpine/latest-stable/main/${ARCH}/{}" && \
    tar -xzf apk-tools-static-*.apk -C / && \
    rm apk-tools-static-*.apk

# 2. Usa a versão estática do apk para instalar o Python com total segurança
RUN /sbin/apk.static add --update --no-cache \
    python3 \
    py3-pip \
    ca-certificates \
    && ln -sf /usr/bin/python3 /usr/bin/python

USER node

# Nota: O CMD ["n8n"] foi removido de propósito. 
# Deixaremos o Docker usar o ENTRYPOINT seguro original da própria imagem do n8n.