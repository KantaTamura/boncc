cmake_minimum_required(VERSION 3.23)
project(boncc C)

#set(CMAKE_VERBOSE_MAKEFILE TRUE)

set(CMAKE_C_STANDARD 11)
set(CMAKE_C_FLAGS "-g -fno-common")

add_library(tokenizer SHARED tokenize.c)
add_library(typer SHARED type.c)
add_library(parser SHARED parse.c)
add_library(codegenerator SHARED codegen.c)

add_executable(boncc main.c)
target_link_libraries(boncc tokenizer typer parser codegenerator)

add_custom_target(test bash ${PROJECT_SOURCE_DIR}/test.sh DEPENDS boncc)
