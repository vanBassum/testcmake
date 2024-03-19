cmake_minimum_required(VERSION 3.0.0)
project(myProject VERSION 0.1.0 LANGUAGES CXX)

# Fetch Catch2 if not already done
include(FetchContent)
FetchContent_Declare(
  Catch2
  GIT_REPOSITORY https://github.com/catchorg/Catch2.git
  GIT_TAG        v3.4.0 # or a later release
)
FetchContent_MakeAvailable(Catch2)

# Create a test executable
add_executable(tests test.cpp)

# Link with Catch2
target_link_libraries(tests PRIVATE Catch2::Catch2WithMain)
