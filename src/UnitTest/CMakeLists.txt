
cmake_minimum_required(VERSION 3.0)

# Locate GTest
find_package(GTest REQUIRED)
include_directories(${GTEST_INCLUDE_DIRS})

include_directories(".")

file(GLOB_RECURSE UNIT_TESTS "*.cpp")
add_executable(unitTests ${UNIT_TESTS})
add_definitions(-DTEST_DATA_DIR="${PROJECT_SOURCE_DIR}/examples/TestData")

target_link_libraries(unitTests ${GTEST_LIBRARIES} pthread ${CMAKE_PROJECT_NAME})
