# Frontend Architecture

## MVC like

## SAM

## EFA(Elegant Frontend Architecture)

### Layered Architecture (top level)

It's not DDD.

Layer should not be aware of any layers above it.


#### Application

- defines oruitng
- builds pages using public compoents from subdomains
- common context (theme, store...)

#### Domain

- bulk of code
- uses UI components
- container, smart components
- has independent subdomains

#### UI

- presentation layer, hosts pure components, reusable, presentational
- agnostic from business requirements, no HTTP requests
- easy components like Button, Table

#### Infrastructure

- wrappers for low level WEB APIs (local storage, geolocation, date)

#### Utils

Language extension utilities.

### Subdomains (medium level)

- Each subdomain provides reusable, self containing building blocks for Application Layer.
- Each domain provides public API
- Avoid assumptions about how Application Layer is consuming public API
- Each subdomains contain private implementation details

### Package scope (low level)

- contained packages exposing public API
- 