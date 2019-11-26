![](https://github.com/iaean/dnssl/workflows/Dockerization/badge.svg)

## dnssl - dockerized DNS infrastructure with SSL certhub

> PowerDNS website : [powerdns.com][1]  
> Certbot website : [certbot.eff.org][2]  
> ISC Bind website : [www.isc.org][3]  
> Opera DNS UI website : [github.com/operasoftware][4]

[1]: https://powerdns.com/
[2]: https://certbot.eff.org/
[3]: https://www.isc.org/downloads/bind/
[4]: https://github.com/operasoftware/dns-ui

**A docker stack to provide a RESTful DNS infrastructure and SSL certificates.**

![figure 1](http://www.plantuml.com/plantuml/proxy?cache=no&src=https://raw.githubusercontent.com/iaean/dnssl/init/assets/figure1.dot)

### Motivation and use case

### Build 'n' Run

### Configuration

### Dependencies

We are using:
* [Alpine][10] as container OS
* Alpine [PowerDNS][11] community packages
* Alpine [Certbot][12] community packages
* [Tini][13] as explicit `init` for containers instead of `--init`
* [mo][15] as [mustache][14] template engine
* [NGINX][16] as ingress HTTP proxy and TCP [loadbalancer][17] with TLS termination or bridging
* [PostgreSQL][18] vanilla from DockerHub
* [Adminer][19] vanilla from DockerHub

[10]: https://alpinelinux.org/
[11]: https://pkgs.alpinelinux.org/package/edge/community/x86_64/pdns
[12]: https://pkgs.alpinelinux.org/package/edge/community/x86_64/certbot
[13]: https://github.com/krallin/tini
[14]: https://mustache.github.io/
[15]: https://github.com/tests-always-included/mo
[16]: https://www.nginx.com/
[17]: https://nginx.org/en/docs/stream/ngx_stream_core_module.html
[18]: https://postgresql.org/
[19]: https://www.adminer.org/

### License

[Apache License Version 2.0](LICENSE)

### Todo

- PowerDNS
  - [ ] add some auth proxy to the API to capture the master token issue
  - [ ] better backup/restore and schema bootstapping
- Certbot
  - [ ] add a real RESTful API for issuance and retrieval
  - [ ] add some auth proxy to the API to capture the master token issue
- Opera DNS UI
  - [ ] fix some PHP issues regarding baseURL handling
  - [ ] add a git hook for pushing the zone file git to an external repository
  - [ ] better backup/restore and schema bootstapping
  - [ ] evaluate [PowerDNS Admin][20] as alternative
- ISC Bind
  - [ ] make ACL and zones configurable

[20]: https://github.com/ngoduykhanh/PowerDNS-Admin

> Written with [StackEdit](https://stackedit.io/).
