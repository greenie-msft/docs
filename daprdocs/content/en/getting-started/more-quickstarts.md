---
type: docs
title: "Try out Dapr quickstarts to learn core concepts"
linkTitle: "More Dapr Quickstarts"
weight: 70
description: "Tutorials with code samples that are aimed to get you started quickly with Dapr"
---

The [Dapr Quickstarts](https://github.com/dapr/quickstarts/tree/v1.0.0) are a collection of tutorials with code samples that are aimed to get you started quickly with Dapr, each highlighting a different Dapr capability.

- A good place to start is the hello-world quickstart, it demonstrates how to run Dapr in standalone mode locally on your machine and demonstrates state management and service invocation in a simple application.
- Next, if you are familiar with Kubernetes and want to see how to run the same application in a Kubernetes environment, look for the hello-kubernetes quickstart. Other quickstarts such as pub-sub, bindings and the distributed-calculator quickstart explore different Dapr capabilities include instructions for running both locally and on Kubernetes and can be completed in any order. A full list of the quickstarts can be found below.
- At anytime, you can explore the Dapr documentation or SDK specific samples and come back to try additional quickstarts.
- When you're done, consider exploring the [Dapr samples repository](https://github.com/dapr/samples) for additional code samples contributed by the community that show more advanced or specific usages of Dapr.

## Quickstarts

| Quickstart               | Description                                                                                                                                                                                    |
|--------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Service Invocation]({{< ref service-invocation-quickstart >}})            | Highlights how to discover and securely invoke methods across services.
| [State Management](https://github.com/dapr/quickstarts/tree/v1.3.0/hello-kubernetes)       | Highlights how to store data as key/value pairs in supported state stores.
| [Publish and Subscribe]({{< ref pubsub-quickstart >}}) | Highlights how to send messages to a topic with one service and subscribe to that topic with another service. 
| [Bindings](https://github.com/dapr/quickstarts/tree/v1.3.0/pub-sub)                | Highlights how to use Dapr bindings to trigger event driven applications and invoke external systems with output bindings.
| [Observability](https://github.com/dapr/quickstarts/tree/v1.3.0/bindings)            | Highlights how to trace and measure the message calls across components and networked services. 
| [Secret Management](https://github.com/dapr/quickstarts/tree/v1.3.0/middleware) | Highlights how to securely retrieve a ssecret from a supported secret store.
| [Actors](https://github.com/dapr/quickstarts/tree/v1.3.0/observability) | Highlights use of Dapr virtual actors to encapsulate code and data in a reusable actor object. 
