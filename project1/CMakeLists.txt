cmake_minimum_required(VERSION 3.10)

PROJECT(proj1)
SET(VTK_DIR c:/MyProjects/VTK-bin)
SET(CMAKE_VERBOSE_MAKEFILE ON)
find_package(VTK REQUIRED)
include(${VTK_USE_FILE} ${VTK_DIR}/Rendering)

add_executable(proj1 proj1)


target_link_libraries(proj1 glu32)
target_link_libraries(proj1 opengl32)
if(VTK_LIBRARIES)
target_link_libraries(proj1 ${VTK_LIBRARIES})
else()
target_link_libraries(proj1 vtkHybrid)
endif()
