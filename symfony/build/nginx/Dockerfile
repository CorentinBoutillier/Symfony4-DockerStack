FROM nginx:1.15-alpine
RUN apk update && apk upgrade && \
    apk add --no-cache bash
COPY default.conf /etc/nginx/conf.d
