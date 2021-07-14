# Load Performance

## Bandwith

How much stuff you can fit through "the internet" per second.

## Latency

How long does it take to get to the other "end of internet". The more latency the longer does it take for TCP to respond.

## Content Distribution Network

Data Stores around the world that cache your application decreasing latency.

## HTTP Caching

- Cache missing - fetch from a server
- Stale - return cache, fetch new from server
- Valid - return cache

Cache-Control Header, only affects `GET`, `OPTIONS`, `HEAD`.

- `no-store` - browser gets a new version every 
- `no-cache` - you can store a copy, but check with a server
- `max-age` - for next X time it's valid
- `s-maxage` - max age for CDN


CDN also cache. Should cache CSS & JSS.

## HTTP/2

[HTTP2](../../fullstack/http/README.md#http/2)

## Service Workers

SW install themselves between server and the app on the browser. They can do a lot of stuff including caching stuff.

## Lazy Loading

Splitting code bundle into chunks and loading them lazily. 

### React

[Lazy loading in React](../react/concepts/code-splitting.md)

### Analyzing Bundles

Webpack Bundle Analyzer

### Slimming dependencies

## Image performance

Load it once load.

## Web fonts



## PWAs

