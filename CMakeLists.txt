cmake_minimum_required(VERSION 3.28)
project(cpp_journey LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

add_compile_options(-Wall -Wextra -Wpedantic)

option(ENABLE_SANITIZERS "Build with AddressSanitizer + UBSan" ON)
if(ENABLE_SANITIZERS)
    add_compile_options(-fsanitize=address,undefined -fno-omit-frame-pointer)
    add_link_options(-fsanitize=address,undefined)
endif()

add_executable(hello src/main.cpp)
add_executable(overflow src/overflow.cpp)
