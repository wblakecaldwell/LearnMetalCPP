# version 3.11 or later of CMake or needed later for installing GoogleTest
# so let's require it now.
cmake_minimum_required(VERSION 3.11-3.18)
project(00_window VERSION 0.1.0)
get_filename_component(ROOT_DIR ../../ ABSOLUTE)
message(STATUS "ROOT_DIR: ${ROOT_DIR}")

set(INCLUDE_DIRS ${ROOT_DIR}/metal-cpp ${ROOT_DIR}/metal-cpp-extensions)
set(SOURCE_FILES 00-window.cpp)

include_directories(${INCLUDE_DIRS})
add_executable(${PROJECT_NAME} ${SOURCE_FILES})
target_link_libraries(${PROJECT_NAME} PUBLIC "-framework Metal -framework Foundation -framework Cocoa -framework CoreGraphics -framework MetalKit")
target_compile_features(${PROJECT_NAME} PUBLIC cxx_std_20)