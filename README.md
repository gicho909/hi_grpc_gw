## reference ##
https://earthly.dev/blog/golang-grpc-example/  
https://grpc-ecosystem.github.io/grpc-gateway/docs/tutorials/introduction/

## precondition ##
go(https://golang.org/dl/)  
protobuf -> protoc   

protoc-gen-go protoc generator plugins  
```
$ go install github.com/grpc-ecosystem/grpc-gateway/v2/protoc-gen-grpc-gateway@latest
$ go install google.golang.org/protobuf/cmd/protoc-gen-go@latest
$ go install google.golang.org/grpc/cmd/protoc-gen-go-grpc@latest
```

$ go mod init  github.com/gicho909/hi_gprc_gw

## code generation ##
```
// generate message type
protoc activity-log/api/v1/*.proto \
   --go_out=. \
   --go_opt=paths=source_relative \
   --proto_path=.example/greetings"

// generate client & server
protoc activity-log/api/v1/*.proto \
    --go-grpc_out=. \
    --go-grpc_opt=paths=source_relative \
    --proto_path=.

protoc activity-log/api/v1/*.proto \
   --go_out=. \
   --go_opt=paths=source_relative \
   --proto_path=.example/greetings" \
   --go-grpc_out=. \
   --go-grpc_opt=paths=source_relative \
   --proto_path=.
```