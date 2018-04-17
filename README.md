# [Dante][dante] SOCKS server as [Docker container](https://hub.docker.com/r/wisdman/dante-server/)

[Dante][dante] is a product developed by Inferno Nettverk A/S. The Dante SOCKS server interoperates with many popular network applications which already have SOCKS support built in to them, such as most web-browsers, instant messaging programs, Telegram, and many others. Developed by Inferno Nettverk A/S, Dante is released under a [BSD/CMU-type license](ftp://ftp.inet.no/pub/socks/LICENSE) and comes with complete source code. This Docker image is released under a [MIT license](LICENSE) and comes with complete configuration files and open user management scripts code.

## Usage

```console
docker pull wisdman/dante-server
docker run -d -p 1080:1080 --restart unless-stopped --name dante-server wisdman/dante-server
```

## Manage users

```console
docker exec -ti dante-server d-adduser <username> [password]
docker exec -ti dante-server d-chpasswd <username> [password]
docker exec -ti dante-server d-deluser <username>
docker exec -ti dante-server d-listuser
```

Password in optional and may be generated automatically

## Test

```console
curl -x socks5://<username>:<password>@localhost:1080 https://google.com
```

## Donation

* PayPal: https://www.paypal.me/wisdman
* BTC: 1862ZyKQLpkrnHC5zN2Xm8UtwW7PEHnFTW
* ETH: 0x1572F3A21487eDD3b88811F87520e8cadB1ee136

## Feedbacks

Suggestions are welcome on [GitHub issue tracker](https://github.com/wisdman/dante-server/issues).

[dante]: https://www.inet.no/dante/index.html
