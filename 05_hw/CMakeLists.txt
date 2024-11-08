cmake_minimum_required(VERSION 3.10)
project(stack)
find_package(GTest REQUIRED)
find_package(benchmark REQUIRED)

add_library(stack stack.cpp)

add_executable(tests tests.cpp)
target_link_libraries(tests PRIVATE GTest::GTest stack)

add_executable(bench bench.cpp)
target_link_libraries(bench PRIVATE benchmark::benchmark stack)

add_executable(main main.cpp)
target_link_libraries(main stack)
