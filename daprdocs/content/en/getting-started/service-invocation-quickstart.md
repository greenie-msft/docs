---
type: docs
title: "Service Invocation QuickStart"
linkTitle: "Service Invocation QuickStart"
weight: 50
description: "Use Dapr's Service Invocation API to call from one service to another service securely"
---

We will now try out some of what Dapr has to offer by using the service invocation API to perform secure service-to-service communication. In the following guide, you will set up two services, the `invoke-caller` and the `invoke-receiver`. The `invoke-caller` will leverage Dapr's service invocation API to call a method defined in the `invoke-receiver` service.

### Select a protocol or language SDK
Select a protocol or SDK example of your choice before getting started with the quickstart. You can learn more about the service invocation building block and how it works in [these docs]({{< ref service-invocation >}}).

{{< tabs "gRPC" "Http" "Python SDK" ".NET SDK" "Java SDK" "Go SDK" "JavaScript SDK" "PHP SDK" >}}
 <!-- gRPC -->
{{% codetab %}}
## TODO gRPC
{{% /codetab %}}

 <!-- Http -->
{{% codetab %}}
## TODO Http
{{% /codetab %}}

 <!-- Python -->
{{% codetab %}}

### Pre-requisites

- [Dapr CLI and initialized environment](https://docs.dapr.io/getting-started)
- [Install Python 3.7+](https://www.python.org/downloads/)

### Install the Dapr Python-SDK
Prior to running this example, install the Dapr Python SDK library:

```bash
pip3 install dapr dapr-ext-grpc
```

### Clone the example

Next, git clone the python-sdk repository:

```bash
git clone git@github.com:dapr/python-sdk.git
```

Once the repository has been cloned, navigate to the invoke-simple project directory:

```bash
cd python-sdk/examples/invoke-simple
```

### Running in self-hosted mode
The Receiver microservice defines the method `mymethod`, which takes a request as an argument and prints the data and metadata of the request. 

Let use the following Dapr CLI command to run the dapr sidecar alongside the `invoker-receiver` service:

```bash
# 1. Start Receiver (expose gRPC server receiver on port 50051)
dapr run --app-id invoke-receiver --app-protocol grpc --app-port 50051 python3 invoke-receiver.py
```

The Caller microservice instantiates the Dapr Client and creates an object of data to send to the receriver service. Then in a loop, the call service invoke the `my-method` method on the invoke-receiver service while sending the data initalized above. 
Use the same CLI command to run the dapr sidecar alongside your python caller service:

```bash
# 2. Start Caller
dapr run --app-id invoke-caller --app-protocol grpc --dapr-http-port 3500 python3 invoke-caller.py
```

Notice in the terminal output that the caller service is repeatedly calling the `mymethod` in the `invoker-receiver` service.

### Inspect the Results
In the terminal window where you ran the the `dapr run` command for the `invoke-caller` service, you will see the output for the response from the `invoker-caller` service after each consecutive call to the `invoke-receiver` service.

```bash
== APP == text/plain
== APP == INVOKE_RECEIVED
== APP == text/plain
== APP == INVOKE_RECEIVED
== APP == text/plain
== APP == INVOKE_RECEIVED
```

In the other terminal shell for the `invoke-receiver` service, you will see the output logged for every request.

```bash
== APP == {'user-agent': ['grpc-go/1.38.0'], 'forwarded': ['for=192.168.0.10;by=192.168.0.10;host=WIN-EH0C40K0610.redmond.corp.microsoft.com'], 'dapr-accept': ['*/*'], 'dapr-content-length': ['35'], 'dapr-content-type': ['application/json; charset=utf-8'], 'traceparent': ['00-3e33ed5ab75dac1d5ec7fe702ea57f19-6b454b19b622482d-01'], 'grpc-trace-bin': [b'\x00\x00>3\xedZ\xb7]\xac\x1d^\xc7\xfep.\xa5\x7f\x19\x01kEK\x19\xb6"H-\x02\x01'], 'dapr-host': ['127.0.0.1:3500'], 'x-forwarded-for': ['192.168.0.10'], 'x-forwarded-host': ['WIN-EH0C40K0610.redmond.corp.microsoft.com']}
== APP == {"id": 1, "message": "hello world"}
```

### Cleanup

```bash
dapr stop --app-id invoke-caller
dapr stop --app-id invoke-receiver
```
### Related Links
* [Python SDK Docs]({{<ref python >}})

{{% /codetab %}}

 <!-- .NET -->
{{% codetab %}}
## TODO .NET
{{% /codetab %}}

 <!-- Java -->
{{% codetab %}}
## TODO Java
{{% /codetab %}}

 <!-- Go -->
{{% codetab %}}
## TODO Go
{{% /codetab %}}

 <!-- JavaScript -->
{{% codetab %}}
## TODO JavaScript
{{% /codetab %}}

 <!-- PHP -->
{{% codetab %}}
## TODO PHP
{{% /codetab %}}

{{< /tabs >}}

{{< button text="Next step: Publish and Subscribe to messages >>" page="pubsub-quickstart" >}}