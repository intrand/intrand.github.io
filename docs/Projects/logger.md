# logger

`logger` is a simple RESTful API that will reflect and log whatever is sent to it, even garbage. It is intentionally not safe for production use.

## Design

I needed a service that could accept any payload at any route and display it in some way. Sometimes appliances or even internal tools don't provide samples of JSON request/response bodies and it's quicker to configure the tool to point to something that can dump it to `stdout` than it is to debug custom client code.

`logger` is just a simple, single-file python `flask` service that runs inside of a `docker` container.

## Status

It's useful from time to time and doesn't require much maintenance, especially thanks to `docker` creating a reproducible environment.
