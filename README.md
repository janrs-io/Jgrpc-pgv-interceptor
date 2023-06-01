# Jgrpc-pgv-interceptor
gRpc-Gateway PGV  中间件

## Usage

```go
	grpcServer := grpc.NewServer(
		grpc.ChainStreamInterceptor(
			// otel 链路追踪
			otelgrpc.StreamServerInterceptor(),
		),
		grpc.ChainUnaryInterceptor(
			// otel 链路追踪
			otelgrpc.UnaryServerInterceptor(),
			// PGV 中间件
			Jgrpc_pgv_interceptor.ValidationUnaryInterceptor,
		),
	)
```
