## Protocol Buffer Basics: Python

https://developers.google.com/protocol-buffers/docs/cpptutorial

## Compile protobuf file to python classes
``` sh
protoc -I=$SRC_DIR --cpp_out=$DST_DIR $SRC_DIR/addressbook.proto
```
