# Jabberwocky API Adapter Layer

This code generated server exposes the [REST API contract](./blob/main/api/swagger.yaml) that is expected to be used by a UI for managing `Connector`s, `Channel`s and `Event Source/Sink`s.

The business logic will be provided by `Camel-K`.

## Prerequisites

You will need to connect to a Kubernetes cluster (also Minikube is fine) where Camel K operator version 1.2 is installed. For the time being this project is supporting also Strimzi Kafka to use the topics as `Channel`s.

## How to run

Build the executable:

```
go build cmd/server/main.go
```

Make sure your Kubernetes cluster is up and running (ie, Minikube), then, launch the local server:

```
go run cmd/server/main.go
```

Test the application browsing the API:

```
$ http http://localhost:8080/v0/connector

[
    {
        "configuration": "some yaml configuration here!",
        "name": "my-connector-1",
        "type": "source"
    },
    {
        "configuration": "some yaml configuration here!",
        "name": "my-connector-2",
        "type": "sink"
    }
]

```
## Caveat

The project is still in prototype phase, structure and dependencies may change.
