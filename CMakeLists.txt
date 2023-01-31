cmake_minimum_required(VERSION 3.24)
project(bcacl C)

set(CMAKE_C_STANDARD 23)

add_library(${PROJECT_NAME} INTERFACE
        source/bcacl.h)
target_include_directories(${PROJECT_NAME} INTERFACE
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/source>
        $<INSTALL_INTERFACE:source/>)

target_compile_features(${PROJECT_NAME} INTERFACE)

option(ENABLE_TESTS OFF)
if (ENABLE_TESTS)
    add_subdirectory(test)
    enable_testing()
endif(ENABLE_TESTS)
