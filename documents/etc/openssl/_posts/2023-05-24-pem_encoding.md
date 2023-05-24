---
title: Key, Cert 파일 .pem 형식으로 인코딩
order: 2
sidebar:
  nav: etc
---

## .key 파일 Encoding

```bash
openssl rsa -in <.key File> -text > key.pem
```



## .crt 파일 Encoding

```bash
openssl x509 -inform PEM -in <.crt File> > cert.pem
```

