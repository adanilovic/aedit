project(atext)

cmake_minimum_required(VERSION 3.5.1)

message(CMAKE_MODULE_PATH = ${CMAKE_MODULE_PATH})

find_package(PkgConfig REQUIRED)
pkg_check_modules(GTK3 REQUIRED gtk+-3.0)
include_directories(${GTK3_INCLUDE_DIRS})
link_directories(${GTK3_LIBRARY_DIRS})
add_definitions(${GTK3_CFLAGS_OTHER})

file(GLOB SOURCES "src/*.cpp")

add_executable(atext ${SOURCES})
target_link_libraries(atext ${GTK3_LIBRARIES})
