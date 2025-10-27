cmake_minimum_required(VERSION 3.16)

# Replace "my_project" with your actual project name if desired
project(my_project VERSION 0.1 LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_POSITION_INDEPENDENT_CODE ON)

# Default build type
if(NOT CMAKE_BUILD_TYPE)
  set(CMAKE_BUILD_TYPE Release CACHE STRING "Build type" FORCE)
endif()

# Source layout
# Expects:
#  - src/main.cpp (executable entry)
#  - include/ (headers)
file(GLOB_RECURSE PROJECT_SOURCES CONFIGURE_DEPENDS *.cpp *.c)
file(GLOB_RECURSE PROJECT_HEADERS CONFIGURE_DEPENDS *.hpp *.h)

if(PROJECT_SOURCES)
  add_executable(${PROJECT_NAME} ${PROJECT_SOURCES} ${PROJECT_HEADERS})
  target_include_directories(${PROJECT_NAME} PRIVATE include)
else()
  message(WARNING "No source files found in /. Add sources or adjust CMakeLists.txt.")
endif()

# Options and packaging
option(BUILD_TESTING "Build tests" OFF)
if(BUILD_TESTING)
  enable_testing()
  # Add test targets here
endif()

message(STATUS "Configured ${PROJECT_NAME} v${PROJECT_VERSION}")
