include(FetchContent)
FetchContent_Declare(
    unity
    GIT_REPOSITORY https://github.com/ThrowTheSwitch/Unity.git
    GIT_TAG v2.6.0
)
FetchContent_MakeAvailable(unity)

add_executable(test_cpu_monitor test_cpu_monitor.c)
target_link_libraries(test_cpu_monitor PRIVATE cpu_monitor unity)

add_test(NAME test_cpu_monitor COMMAND test_cpu_monitor)
