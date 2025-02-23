cmake_minimum_required(VERSION 3.15)

if (WIN32)
    message("Compiling on Windows? :) Please use MSVC for compiling.")
    set(VCPKG_TARGET_TRIPLET "x64-windows")
    SET(CMAKE_TOOLCHAIN_FILE "D:/vcpkg/scripts/buildsystems/vcpkg.cmake")
    include("D:/vcpkg/scripts/buildsystems/vcpkg.cmake")
else ()
    message("Compiling on Linux? :3")
endif ()

project(server DESCRIPTION "Core Server Project of Arcane")

set(CXXFLAGS  "")
set(CMAKE_CXX_FLAGS "${CXXFLAGS}")

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_C_STANDARD 11)

set(REDIS_PLUS_PLUS_BUILD_TEST OFF)
set(REDIS_PLUS_PLUS_CXX_STANDARD 20)

set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR})
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR})

add_subdirectory(Src)
add_subdirectory(Dependencies)

# libsfml-dev
# sudo apt-get install libx11-dev libflac-dev libvorbis-dev libopenal-dev libudev-dev freeglut3-dev xorg-dev xvfb libgl1-mesa-dri libgl1-mesa-glx
#Xvfb :0 -screen 0 3200x1920x24&
#export DISPLAY=:0
