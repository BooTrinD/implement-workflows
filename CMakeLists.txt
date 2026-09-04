cmake_minimum_required(VERSION 3.16)
project(cpu_monitor C)

set(CMAKE_C_STANDARD 11)
set(CMAKE_C_STANDARD_REQUIRED ON)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

add_library(cpu_monitor src/cpu_monitor.c)
target_include_directories(cpu_monitor PUBLIC src)

add_executable(cpu_monitor_app src/main.c)
target_link_libraries(cpu_monitor_app PRIVATE cpu_monitor)
target_compile_options(cpu_monitor_app PRIVATE -Wall -Wextra)

enable_testing()
add_subdirectory(tests)
