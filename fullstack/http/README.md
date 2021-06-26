# HTTP

- [Fullstack](../README.md)
- [Headers](./headers.md)
- [HTTPS](./https.md)
- [Request & Response](./request-response.md)

## What's HTTP?

Hypertext Transport Protocol - standard how code moves between server and a client. It works over TCP.

Works on [Request](./request-response.md#request) and [Response](./request-response.md#response).

## HTTP/2

Requires HTTPS, extension of SPD protocol, allows multiplexing.

### Multiplexing

Combination of multiple request. So we make one connection and request multiple things during it.

![image](https://user-images.githubusercontent.com/20524370/123518713-740fb100-d6a7-11eb-97ae-2d4aa6a86cb6.png)

![image](https://user-images.githubusercontent.com/20524370/123518758-ae794e00-d6a7-11eb-9897-6cddd107aa1c.png)

Most browsers are limited to 6 connections.

### HPACK

Compression algorithms that compresses headers into a hash.

## HTTP/3

Runs on UDP - allows for quick internet connections. If we care about speed more than error correction then it's good to use it.
