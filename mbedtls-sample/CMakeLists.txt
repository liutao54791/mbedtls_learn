cmake_minimum_required(VERSION 3.5)
project(mbedtls_sample C)

set(CMAKE_C_STANDARD 99)

include_directories(./ mbedtls-2.12/include)

# 增加mbedtls源文件
aux_source_directory(mbedtls-2.12/library MBEDTLS_SOURCES)
add_definitions(-DMBEDTLS_CONFIG_FILE=<mbedtls_config.h>)

add_executable(mbedtls_sample ${MBEDTLS_SOURCES} main.c)
