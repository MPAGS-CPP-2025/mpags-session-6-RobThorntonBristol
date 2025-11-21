# Set CMake requirements then declare project
cmake_minimum_required(VERSION 3.8)
project(MPAGSCipher VERSION 0.1.0)

# Output all command lines when MAkeFiles are generated
set(CMAKE_VERBOSE_MAKEFILE ON)

# Specifics of our build
set(CMAKE_CXX_EXTENSIONS OFF)
set(CMAKE_CXX_FLAGS "-Wall -Wextra -Werror -Wfatal-errors -Wshadow -pedantic")

# Declare the build of mpags-cipher main program
add_executable(mpags-cipher mpags-cipher.cpp
    MPAGSCipher/TransformChar.hpp
    MPAGSCipher/TransformChar.cpp
    MPAGSCipher/processCommandLine.hpp
    MPAGSCipher/processCommandLine.cpp
)

target_include_directories(mpags-cipher PRIVATE MPAGSCipher)
target_compile_features(mpags-cipher PRIVATE cxx_std_17)
