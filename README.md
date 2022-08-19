# IOAM Collector (golang interface for Jaeger)

The IOAM Collector is used inside the [Cross-Layer Telemetry](https://github.com/Advanced-Observability/cross-layer-telemetry) (CLT) project.

Its role is to enhance OpenTelemetry traces and spans for a specific backend (in
this case, Jaeger) with IOAM data.

By default, it listens on port **7123**.

## Install

Please make sure that golang and its environment are already installed. For this
example, golang version **1.19** was used.

### IOAM API

Get the IOAM API (proto3) file **for Cross-Layer Telemetry** (CLT branch):
```[bash]
wget https://raw.githubusercontent.com/Advanced-Observability/ioam-api/clt/ioam_api.proto
```

And generate its `go` files:
```[bash]
protoc --go_out=. --go-grpc_out=. ioam_api.proto
```

### Dependencies

Automatically download dependencies:
```
go mod init ioam-collector
go mod tidy
```

## Run it!

Either run it directly:
```
go run ioam-collector.go
```

Or compile it and run the executable:
```
go build ioam-collector.go
./ioam-collector
```
