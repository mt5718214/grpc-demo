clean:
	rm pb/*.pb.go

gen:
	@$(MAKE) clean
	protoc \
	-I=protos \
	--go_out=pb \
	--go_opt=paths=source_relative \
	--go-grpc_out=pb \
	--go-grpc_opt=paths=source_relative \
	protos/*.proto \

run:
	go run main.go