cmake_minimum_required(VERSION 3.0.0)

project(Calculator_Project VERSION 1.0.0)

add_library(my_math
addition.cpp
division.cpp)

add_library(my_print
print_result.cpp)

add_executable(calculator
main.cpp)

add_executable(calculator_dup
main.cpp)

target_link_libraries(calculator PRIVATE my_math my_print)
target_link_libraries(calculator_dup PRIVATE my_math my_print)