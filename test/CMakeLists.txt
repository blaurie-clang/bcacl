cmake_minimum_required(VERSION 3.24)

find_package(CMocka)
include_directories(${CMOCKA_INCLUDE_DIR})

add_executable(bcacl_test main.c)

target_link_libraries(bcacl_test
        ${CMOCKA_LIBRARIES}
        bcacl)
