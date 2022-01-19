cmake_minimum_required(VERSION 3.20)
project(protobuf-cpp-demo)

set(CMAKE_CXX_STANDARD 14)

# If you encounter some protobuf version issue on your system, define the protoc binary explicity
# set(Protobuf_PROTOC_EXECUTABLE /usr/bin/protoc)
include(FindProtobuf)
find_package(Protobuf REQUIRED)
include_directories(${PROTOBUF_INCLUDE_DIR})

add_library(address STATIC addressbook.pb.cc)
target_link_libraries(address ${PROTOBUF_LIBRARY})

add_executable(add_people add_people.cpp)
target_link_libraries(add_people address ${CMAKE_THREAD_LIBS_INIT})

add_executable(list_people list_people.cpp)
target_link_libraries(list_people address ${CMAKE_THREAD_LIBS_INIT})
