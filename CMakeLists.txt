cmake_minimum_required(VERSION 3.10)

# set compiler path
if(NOT APPLE)
    set(CMAKE_C_COMPILER "/opt/llvm-project/build/bin/clang")
    set(CMAKE_CXX_COMPILER "/opt/llvm-project/build/bin/clang++")
endif()

set(CMAKE_CXX_STANDARD 11)

# set build type
if(NOT CMAKE_BUILD_TYPE)
    set(CMAKE_BUILD_TYPE Debug)
endif()

# project name
project(LINEAR-BLUR CXX)

# halide
if(APPLE)
    set(HALIDE_DISTRIB_DIR "/Users/xxx/Library/Halide/build/install/")
else()
    set(HALIDE_DISTRIB_DIR "/opt/Halide/build/install/")
endif()
include("${HALIDE_DISTRIB_DIR}/halide.cmake")

add_subdirectory(src)








