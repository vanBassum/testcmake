cmake_minimum_required(VERSION 3.0.0)
project(myProject VERSION 0.1.0 LANGUAGES CXX)

# Add main executable
add_executable(myProject "main.cpp")

# Enable testing
include(CTest)
enable_testing()

# Add tests from the test directory
add_subdirectory(test)

# Set CPack details
set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)
