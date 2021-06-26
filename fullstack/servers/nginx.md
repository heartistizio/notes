# Nginx

Nginx(engine-x) is a lightweight, extremely fast web server. Helps route requests to the right thing. Can handle more requests than server.

Can play roles of:

- reverse proxy
- proxy server
- file server
- caching
- performance tuning
- compress file
- encryption

## Web server

Receives web traffic and does something with it.

## Configuration

### Install

```sh
sudo apt install nginx
sudo service nginx start
```

### Base directory for requests

```nginx
root /var/www/html;
```

### Location block

```nginx
location / {
    try_files $uri $uri/ =404;
}
```

Here - using regular expression server a determined file, if that fails serves a 404.

### Directive

Macro for doing something.

```nginx
try_files
```

### Redirect

```nginx
location /help {
    return 301 https://developer.mozilla.org/en-US/;
}
```

### Subdomain

Nginx can create many servers on one server.

```nginx
server {
    listen 80;
    listen [::]80; # IPV6 notation

    server_name test.gojo.one;

    location / {
        proxy_pass http://localhost:3000;
    }
}
```

### File compression

Nginx automatically compresses and unpacks files sent by default.

`/etc/nginx/nginx.conf`
