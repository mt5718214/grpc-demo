clean:
	rm pb/*.pb.go

gen:
	@$(MAKE) clean
	protoc \
	--go_out=pb \
	--go_opt=paths=source_relative \
	--go-grpc_out=pb \
	--go-grpc_opt=paths=source_relative \
	processor_message.proto

run:
	go run main.go