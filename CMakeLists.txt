cmake_minimum_required(VERSION 3.0.0)
project(testp VERSION 0.1.0 LANGUAGES CXX)

# Enable testing
include(CTest)
enable_testing()

# Add main executable
add_executable(testp main.cpp)

# Fetch Catch2
include(FetchContent)
FetchContent_Declare(
  Catch2
  GIT_REPOSITORY https://github.com/catchorg/Catch2.git
  GIT_TAG        v3.4.0 # or a later release
)
FetchContent_MakeAvailable(Catch2)

# Add test executable
add_executable(tests test/test.cpp)

# Link with Catch2
target_link_libraries(tests PRIVATE Catch2::Catch2WithMain)

# Set CPack details
set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)
