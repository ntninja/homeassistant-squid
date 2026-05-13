ARG BUILD_FROM
FROM ${BUILD_FROM}

# Install Squid, OpenSSL (certs), apache2-utils (auth), and certbot
# Install Squid, OpenSSL, Auth, Python3, and build dependencies for latest Certbot
RUN apk add --no-cache squid openssl apache2-utils python3 py3-pip py3-flask py3-gunicorn \
    gcc musl-dev python3-dev libffi-dev openssl-dev && \
    python3 -m pip install --no-cache-dir --break-system-packages certbot

# Copy data for add-on
# Copy data for add-on
COPY run.sh /
COPY monitoring /monitoring

RUN chmod a+x /run.sh

CMD [ "/run.sh" ]
