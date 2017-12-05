# Datadog Example

This repository contains an example Go app that is instrumented using the new
[OpenTracing API][1] available in the [Datadog Go Client][2].

## Requirements

* Go 1.7 or later
* [dep](https://github.com/golang/dep)
* Install ``docker`` and ``docker-compose`` on your system. Please, follow the instructions available
  in the [Docker website](https://www.docker.com/community-edition)
* A [Datadog Account](https://app.datadoghq.com/signup)
* A Datadog ``API_KEY`` that you can create from the [Datadog API page](https://app.datadoghq.com/account/settings#api).
  Remember to not share this key with anyone.

## Initialize dependencies

This project uses `dep` to handle dependencies. To prepare your `vendor` folder,
launch from your shell::

    $ dep ensure

## Run the example

You should have a running [Datadog Agent](https://github.com/DataDog/dd-agent) to submit traces.
To run a Datadog Agent, launch the following command::

    $ DD_API_KEY=<API_KEY> docker-compose up

and then you can launch the Go server with::

    $ go run main.go

To generate traces, you can simply call your endpoint from another shell::

    $ curl localhost:3000/account/42

[1]: https://github.com/opentracing/opentracing-go
[2]: https://github.com/DataDog/dd-trace-go
