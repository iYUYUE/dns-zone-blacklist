FROM alpine:latest

RUN apk add --no-cache bats bind bind-tools dnsmasq unbound

COPY ./dns-zone-blacklist-test.sh /

RUN chmod +x /dns-zone-blacklist-test.sh

CMD ["/dns-zone-blacklist-test.sh"]
