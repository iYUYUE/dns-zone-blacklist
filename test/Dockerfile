FROM alpine:latest

RUN apk add --no-cache bats bind bind-tools dnsmasq unbound

RUN chmod +x /dns-zone-blacklist/test/dns-zone-blacklist-test.sh

CMD ["/dns-zone-blacklist/test/dns-zone-blacklist-test.sh"]
