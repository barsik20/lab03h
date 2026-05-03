cmake_minimum_required(VERSION 3.4)
project(hello_world)
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(FORMATTER_LIB_PATH ${CMAKE_CURRENT_SOURCE_DIR}/../formatter_lib)
set(FORMATTER_EX_LIB_PATH ${CMAKE_CURRENT_SOURCE_DIR}/../formatter_ex_lib)
add_executable(hello_world main.cpp)
target_include_directories(hello_world PRIVATE
    ${FORMATTER_LIB_PATH}
    ${FORMATTER_EX_LIB_PATH}
)
target_link_directories(hello_world PRIVATE
    ${FORMATTER_LIB_PATH}/_build
    ${FORMATTER_EX_LIB_PATH}/_build
)
target_link_libraries(hello_world
    formatter_ex_lib
    formatter_lib
)
