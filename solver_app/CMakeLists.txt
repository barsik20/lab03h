cmake_minimum_required(VERSION 3.4)
project(solver_app)
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
add_executable(solver_app main.cpp)
target_include_directories(solver_app PRIVATE
    ${CMAKE_CURRENT_SOURCE_DIR}/../formatter_lib
    ${CMAKE_CURRENT_SOURCE_DIR}/../formatter_ex_lib
    ${CMAKE_CURRENT_SOURCE_DIR}/../solver_lib
)
target_link_directories(solver_app PRIVATE
    ${CMAKE_CURRENT_SOURCE_DIR}/../formatter_lib/_build
    ${CMAKE_CURRENT_SOURCE_DIR}/../formatter_ex_lib/_build
    ${CMAKE_CURRENT_SOURCE_DIR}/../solver_lib/_build
)
target_link_libraries(solver_app 
    formatter_ex_lib
    formatter_lib 
    solver_lib
)
