FROM alpine:latest

RUN apk update && apk add --no-cache --upgrade bash \
&& apk add --no-cache --repository=http://dl-cdn.alpinelinux.org/alpine/edge/main libc6-compat

RUN wget https://dl.grafana.com/oss/release/grafana-6.6.0.linux-amd64.tar.gz \
&& tar -zxvf grafana-6.6.0.linux-amd64.tar.gz

RUN mkdir /grafana-6.6.0/data
COPY grafana.db /grafana-6.6.0/data/grafana.db

EXPOSE 3000
CMD cd ./grafana-6.6.0/bin/ && ./grafana-server