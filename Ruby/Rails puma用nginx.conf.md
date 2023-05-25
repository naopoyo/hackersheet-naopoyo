---
name: "Rails puma"
slug: "vymjnmg"
emoji: "🎃"
tags: ["Ruby", "nginx"]
---

# Rails puma

## puma

[A Fast, Concurrent Web Server for Ruby & Rack - Puma](https://puma.io/)

## nginx

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

