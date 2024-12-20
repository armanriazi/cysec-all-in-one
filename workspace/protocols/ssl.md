## Make secure your server

• Configuration generator by [Mozilla](https://mozillaigithubio/server-side-tIsissl-config-generator/)
• Further detalis: [Server](https://wiki.mozilla.org/Security/Server) Side TLS, [Crypt Setup](https://gitlab.com/cryptsetup/cryptsetup)

## Install

```bash
wget -c https://www.openssl.org/source/openssl-1.0.2p.tar.gz
tar -xzvf openssl-1.0.2p.tar.gz
```

```bash
openssl req -newkey rsa:2048 -nodes -keyout /etc/ssl/private/rancher.yourdomain.ir.key -x509 -days 365 -out /etc/ssl/certs/rancher.yourdomain.ir.crt
openssl req -newkey rsa:4096 -new -nodes -x509 -days 365 -keyout ./private/cakey.pem -out cacert.pem
openssl req -new -newkey rsa:2048 -nodes -keyout ./requests/rancher.yourdomain.ir.pem -out ./requests/rancher.yourdomain.ir.csr
```

```bash
openssl ca -in rancher.yourdomain.ir.csr -out rancher.yourdomain.ir.crt
openssl x509 -text -noout -in /root/ca/cacerts.pem
openssl s_client -showcerts -connect rancher.yourdomain.ir:443
```
