cmake_minimum_required(VERSION 3.1)
project(test_package)

include(${CMAKE_BINARY_DIR}/conanbuildinfo.cmake)
conan_basic_setup(TARGETS)

find_package(ghc_filesystem REQUIRED CONFIG)

add_executable(${PROJECT_NAME} test_package.cpp)
target_link_libraries(${PROJECT_NAME} ghcFilesystem::ghc_filesystem)
set_target_properties(${PROJECT_NAME} PROPERTIES CXX_STANDARD 11)
