---
name: "Rails puma用nginx.conf"
slug: "vymjnmg"
---

# Rails puma用nginx.conf

```nginx
upstream puma {
  server unix:///app/sockets/puma.sock;
}
```

```nginx
server {
    listen 80;
    server_name puma;
}
```

