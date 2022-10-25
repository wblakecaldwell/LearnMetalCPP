cmake_minimum_required(VERSION 3.11-3.18)
project(LearmMetaCPP VERSION 0.1.0)

include(CTest)
enable_testing()

add_subdirectory(learn-metal/00-window)
add_subdirectory(learn-metal/01-primitive)
add_subdirectory(learn-metal/02-argbuffers)
add_subdirectory(learn-metal/09-compute-to-render)

set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)
