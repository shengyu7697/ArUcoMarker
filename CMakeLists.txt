project(MarkerVR)
cmake_minimum_required(VERSION 3.0)

set(CMAKE_BUILD_TYPE Debug)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)
set(BUILD_SHARED_LIBS ON)

option(USE_PROTOBUF "use protobuf?" ON)

if(WIN32)
else()
    set(CMAKE_CXX_FLAGS_DEBUG "-O0 -g -std=c++11")
    set(CMAKE_CXX_FLAGS_RELEASE "-W -Wall -O3 -std=c++11")
endif()

find_package(OpenCV)

add_subdirectory(src/MarkerCreator)

add_subdirectory(src/MarkerDetector)

add_subdirectory(src/MarkerVR)
