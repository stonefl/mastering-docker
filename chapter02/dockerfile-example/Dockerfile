
FROM alpine:latest
LABEL maintainer="Lei Feng <leifeng@fedex.com>"
LABEL description="This example Dockerfile installs NGINX."

# set proxy
ENV HTTPS_PROXY="https://internet.proxy.fedex.com:3128"
ENV HTTP_PROXY="http://internet.proxy.fedex.com:3128"

RUN apk add --update nginx && \
        rm -rf /var/cache/apk/* && \
        mkdir -p /tmp/nginx/

COPY files/nginx.conf /etc/nginx/nginx.conf
COPY files/default.conf /etc/nginx/conf.d/default.conf
ADD files/html.tar.gz /usr/share/nginx/

EXPOSE 80/tcp

ENTRYPOINT ["nginx"]
CMD ["-g", "daemon off;"]