cmake_minimum_required(VERSION 3.18.2 FATAL_ERROR)

set(PROJECT_NAME AniEngine)

project(${PROJECT_NAME})

set(CMAKE_CXX_STANDARD 17)

add_executable(${PROJECT_NAME} 
   src/main.cpp
   src/Renderer/ShaderProgram.cpp
   src/Renderer/ShaderProgram.h)

set(GLFW_BUILD_DOCS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)
set(GLFW_INSTALL OFF CACHE BOOL "" FORCE)

add_subdirectory(ext/glfw)
target_link_libraries(${PROJECT_NAME} glfw)

add_subdirectory(ext/glad)
target_link_libraries(${PROJECT_NAME} glad)