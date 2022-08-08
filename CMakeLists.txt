cmake_minimum_required(VERSION 3.23)
project(boncc C)

set(CMAKE_C_STANDARD 11)
set(CMAKE_C_FLAGS "-g -fno-common")

add_executable(boncc main.c)
add_custom_target(test bash ${PROJECT_SOURCE_DIR}/test.sh DEPENDS boncc)
