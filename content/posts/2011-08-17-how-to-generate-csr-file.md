---
categories:
- security
- system
date: '2011-08-17T14:23:26+00:00'
title: How to generate CSR file

---
You can generate CSR using OpenSSL:

```sh
openssl req -newkey rsa:2048 -keyout private_key.pem -out server.csr
```

where `req` is a command to control x.509 certificates,
  
`-newkey` &#8212; means _"we need a new key"_
  
`_rsa_` &#8212; hashing algorythm, and _2048_ &#8212; the length of a key. To sign certificates after 2010 you need at least this length! Until 2010 it was possible to use _1024_ bit key.
  
`-keyout` &#8212; path to the file on the server
  
`-out` &#8212; path to the certificate's request file (_crs_)
