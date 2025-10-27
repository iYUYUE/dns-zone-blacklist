# DNS Zone Blacklist Generator

This project generates a zone file for [BIND](https://en.wikipedia.org/wiki/BIND), [Dnsmasq](https://en.wikipedia.org/wiki/Dnsmasq) and [Unbound](https://en.wikipedia.org/wiki/Unbound_(DNS_server)) DNS servers using data from the [ShadowWhisperer/BlockLists](https://github.com/ShadowWhisperer/BlockLists) project. The generated zone files can be used to block ads and malware for an entire network when used with a local DNS server.

DNS based ad blockers can support wildcard entries. This tool filters out any subdomains of known adware or malware domains, reducing the number of zone entries required from **404,757** down to **24,109**.

| DNS Server | Response Type | Download  | SHA256 Checksum |
| ---------- |:-------------:|:---------:|:---------------:|
| BIND | 0.0.0.0 | [link](https://raw.githubusercontent.com/iYUYUE/dns-zone-blacklist/master/bind/zones.blacklist) | [link](https://raw.githubusercontent.com/iYUYUE/dns-zone-blacklist/master/bind/zones.blacklist.checksum) |
| BIND (RPZ) | NXDOMAIN | [link](https://raw.githubusercontent.com/iYUYUE/dns-zone-blacklist/master/bind/bind-nxdomain.blacklist) | [link](https://raw.githubusercontent.com/iYUYUE/dns-zone-blacklist/master/bind/bind-nxdomain.blacklist.checksum) |
| Dnsmasq | 0.0.0.0 | [link](https://raw.githubusercontent.com/iYUYUE/dns-zone-blacklist/master/dnsmasq/dnsmasq.blacklist) | [link](https://raw.githubusercontent.com/iYUYUE/dns-zone-blacklist/master/dnsmasq/dnsmasq.blacklist.checksum) |
| Dnsmasq | NXDOMAIN | [link](https://raw.githubusercontent.com/iYUYUE/dns-zone-blacklist/master/dnsmasq/dnsmasq-server.blacklist) | [link](https://raw.githubusercontent.com/iYUYUE/dns-zone-blacklist/master/dnsmasq/dnsmasq-server.blacklist.checksum) |
| Unbound | 0.0.0.0 | [link](https://raw.githubusercontent.com/iYUYUE/dns-zone-blacklist/master/unbound/unbound.blacklist) | [link](https://raw.githubusercontent.com/iYUYUE/dns-zone-blacklist/master/unbound/unbound.blacklist.checksum) |
| Unbound | NXDOMAIN | [link](https://raw.githubusercontent.com/iYUYUE/dns-zone-blacklist/master/unbound/unbound-nxdomain.blacklist) | [link](https://raw.githubusercontent.com/iYUYUE/dns-zone-blacklist/master/unbound/unbound-nxdomain.blacklist.checksum) |

## Building the Blacklist

The blacklist can be generated using [Node.js 8.4.0](https://nodejs.org) or later.

Install:

```
git clone https://github.com/iYUYUE/dns-zone-blacklist.git
cd dns-zone-blacklist

npm install
```

Then build:

```
node build.js
```

The compiled blacklist files will be saved to the `./bind`, `./dnsmasq` and `./unbound` a directories in the root of the project.

### Custom Entries

Custom entries can be added to the custom.blacklist.json file in the root of this project before building.

### Whitelist

Any domains you wish to exclude from the blacklist can be added to the custom.whitelist.json file in the root of this project before building.
