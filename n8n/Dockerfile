FROM n8nio/n8n:2.14.2

USER root

# 1. Recuperando o instalador apk de uma imagem Alpine pura
COPY --from=alpine:latest /sbin/apk /sbin/apk
COPY --from=alpine:latest /usr/lib/libapk.so* /usr/lib/
COPY --from=alpine:latest /etc/apk /etc/apk

# 2. Agora que o apk está de volta, podemos instalar o Python!
RUN apk update && apk add --no-cache \
    python3 \
    py3-pip \
    ca-certificates \
    && ln -sf /usr/bin/python3 /usr/bin/python

USER node

# O entrypoint já está definido na imagem base, então só o CMD basta
CMD ["n8n"]