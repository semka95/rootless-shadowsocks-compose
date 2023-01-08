## Steps to run Shadowsock-rust in rootless docker:
1. Copy systemd service file to default folder and run it:
```bash
cp shadowsocks-rootless-compose.service ~/.config/systemd/user/
systemctl --user enable --now shadowsocks-rootless-compose.service
```
2. Open port `8388`:
```bash
sudo ufw allow 8388
```
Run on local pc:
```bash
sslocal -b "127.0.0.1:1080" -s "your_server_ip:8388" -m "chacha20-ietf-poly1305" -k "password" --plugin "v2ray-plugin" --plugin-opts "server"
```

TODO:
- use xray or simple-tls

Links:
- [simple-tls](https://github.com/IrineSistiana/simple-tls)
- [Shadowsocks-rust docker image with v2ray](https://hub.docker.com/r/teddysun/shadowsocks-rust)
- [Shadowsocks-rust repository](https://github.com/shadowsocks/shadowsocks-rust)
- [Server with shadowsocks-rust + v2ray (websocket-http) + simple-tls (TLS1.3)](https://github.com/MrKsey/ss-tls-v2ray), [instruction](https://4pda.to/forum/index.php?showtopic=744431&st=3520#entry114436262)
- [Shadowsocks over Cloudflare](https://medium.com/@telecom_angel/%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-vpn-%D0%BD%D0%B0-%D0%BE%D1%81%D0%BD%D0%BE%D0%B2%D0%B5-shadowsocks-%D1%87%D0%B5%D1%80%D0%B5%D0%B7-cloudflare-cdn-2ff7499fd9fa)
