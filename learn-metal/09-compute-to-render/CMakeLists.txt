# version 3.11 or later of CMake or needed later for installing GoogleTest
# so let's require it now.
cmake_minimum_required(VERSION 3.11-3.18)
project(09-compute-to-render VERSION 0.1.0)
get_filename_component(ROOT_DIR ../../ ABSOLUTE)
message(STATUS "ROOT_DIR: ${ROOT_DIR}")

set(INCLUDE_DIRS ${ROOT_DIR}/metal-cpp ${ROOT_DIR}/metal-cpp-extensions)
set(SOURCE_FILES 09-compute-to-render.cpp)

include_directories(${INCLUDE_DIRS})
add_executable(${PROJECT_NAME} ${SOURCE_FILES})
target_link_libraries(${PROJECT_NAME} PUBLIC "-framework Metal -framework Foundation -framework Cocoa -framework CoreGraphics -framework MetalKit")
target_compile_features(${PROJECT_NAME} PUBLIC cxx_std_20)