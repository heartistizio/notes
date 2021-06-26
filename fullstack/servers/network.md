# Network

## Port

Communication endpoint that maps to a specific process or network service.

## IP Tables

Ways of routing, blocking or denying request to certain ports.

## Uncomplicated Firewall

```sh
            http
            https
$ ufw allow ssh
      deny
      reject
```

`deny` - blackholes request.
`reject` - rejects request explicitly.
