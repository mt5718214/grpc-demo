**當寫好.proto檔案後, 可透過protocol buffer compiler （protoc）來產生Java, Kotlin, Python, C++, Go, Ruby, Objective-C, or C# 等等的code**

Note: 對於Go, 要產生代碼還需要為protoc安裝額外的plugin

1. 安裝protoc, 可使用brew安裝 `brew install protobuf`
2. **Go Protocol Buffers Plugin**：需要安裝 Go 的 Protocol Buffers 插件，以便 protoc 可以生成 Go 語言的程式碼。使用指令來安裝插件：
`go install google.golang.org/protobuf/cmd/protoc-gen-go@v1.28`
3. **Go gRPC Plugin**：需要安裝 Go 的 gRPC 插件，以便 protoc 可以生成 gRPC 相關的程式碼。使用指令來安裝插件：`go install google.golang.org/grpc/cmd/protoc-gen-go-grpc@v1.2`


```bash
# 使用 Protocol Buffers 的 protoc 工具生成 Go 語言的程式碼，以及 gRPC 相關的程式碼。
$ protoc \
-I=protos \
--go_out=pb \
--go_opt=paths=source_relative \
--go-grpc_out=pb \
--go-grpc_opt=paths=source_relative \
protos/*.proto

# IMPORT_PATH或-I: 告訴 protoc 編譯器在特定目錄中搜索 .proto 檔案。

# --go_out=.：指定生成 Go 語言程式碼的輸出目錄。. 表示當前目錄，也就是指令所在的目錄。生成的 Go 檔案將被放置在當前目錄中。

# --go_opt=paths=source_relative：用於設置生成的 Go 檔案的路徑相對於源文件的路徑。這樣生成的 Go 檔案將保持與源文件相同的目錄結構。

# --go-grpc_out=.：指定生成 gRPC 相關程式碼的輸出目錄，這些程式碼用於支援 gRPC 功能。. 表示當前目錄，生成的 gRPC 檔案將被放置在當前目錄中。

# --go-grpc_opt=paths=source_relative：設置生成的 gRPC 檔案的路徑相對於源文件的路徑，保持與源文件相同的目錄結構。
```