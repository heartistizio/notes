# Concepts

## Why care about performance

Performance has direct impact on users:
- 100 ms - gold standard, user feels that response is instant
- 1 s - limit of when user will notice delay, but not have the flow of thought interrupted
- 10 s - almost impossible to keep user attention

Research: 
- 1 second slow down results in 11% fewer page views, 7% less conversion [Aberdeen Group](missing-link)
- 2 second delay in web page load time increases bounce rates by 103 percent [Akamai](missing-link)
- 400 ms improvement in performance resulted in 9% increase in traffic at [Yahoo](missing-link)
- 2% slower page results in 2% fewer searches [Google](missing-link)
- 100 ms improvement in performance results in 1% increase in overall revenue [Amazon](missing-link)
- to make the application feel faster than competitors you need to be 20% faster

## Application Needs

Three kinds of performance:

- [Network Load Performance](./load.md)
- [Parsing, compilation and JS Performance](./js.md)
- [Rendering Performance](./render.md)

Sites that focus on showing content should focus on being static and fast. They should focus on the Load Performance.

Sites that need a lot of interaction should work on their JS and rendering performance a bit more than others.


### RAIL

Ideal model of performant application.

#### Response

Click to paint in less than `100 ms`.

#### Animation

Each frame completes in less than `16 ms`. 

Drag to paint in less than `16 ms`.

#### Idle

Use idle to proactively schedule work.

Complete work in  `50 ms` chunks.

#### Load

Satisfy the `Response` goals during full load.

Get first meaningful paint in` 1000 ms`.

## Metrics

- testing on different devices
- simulating network cnoditions
- performance budget

## Dev Tools Performance

- summary
- flame chart
