﻿cmake_minimum_required(VERSION 3.17)
project(test)

set(CMAKE_CXX_STANDARD 14)

#拷贝depends目录
file(COPY "../../../template/depends/lua/" DESTINATION "../depends/lua/")
file(COPY "../../../template/depends/LuaBridge/" DESTINATION "../depends/LuaBridge/")

#头文件目录
include_directories("depends/lua/src")
include_directories("depends")

file(GLOB_RECURSE SOURCES "depends/lua/src/*.c")

add_executable(test ${SOURCES} "main.cpp")