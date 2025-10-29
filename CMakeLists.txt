cmake_minimum_required(VERSION 3.10)

project(HelloWorld)

set(CMAKE_CXX_STANDARD 11)

# Enable testing
enable_testing()

# Main executable
add_executable(${PROJECT_NAME} main.cpp math_operations.cpp)

# Google Test
include(FetchContent)
FetchContent_Declare(
    googletest
    URL https://github.com/google/googletest/archive/03597a01ee50ed33e9fd7188e49b65d86e61e2f0.zip
)
FetchContent_MakeAvailable(googletest)

# Unit tests
add_executable(unit_tests tests/unit_tests.cpp math_operations.cpp)
target_link_libraries(unit_tests GTest::gtest_main)
add_test(NAME unit_tests COMMAND unit_tests)
