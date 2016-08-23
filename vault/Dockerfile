FROM alpine:latest

MAINTAINER Docker SaaS Team <SaaS@docker.com>

ENV VAULT_VERSION 0.6.0
ENV VAULT_TMP_FILE /tmp/vault.zip

ADD https://releases.hashicorp.com/vault/${VAULT_VERSION}/vault_${VAULT_VERSION}_linux_amd64.zip ${VAULT_TMP_FILE}

RUN cd /bin && unzip ${VAULT_TMP_FILE} && chmod +x /bin/vault && rm ${VAULT_TMP_FILE}

EXPOSE 8200
ENV VAULT_ADDR "http://127.0.0.1:8200"

ENTRYPOINT ["/bin/vault"]
CMD "server"
