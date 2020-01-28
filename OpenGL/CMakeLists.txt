cmake_minimum_required(VERSION 3.14)
project(OpenGL)

set(CMAKE_CXX_STANDARD 14)

add_executable(OpenGL main.cpp src/window.cpp)

add_subdirectory(dependencies/glfw-3.3.2)
add_subdirectory(dependencies/glew-2.1.0/build/cmake)

target_include_directories(OpenGL PRIVATE ${PROJECT_SOURCE_DIR}/dependencies/glew-2.1.0/include)

target_link_libraries(OpenGL glfw)
target_link_libraries(OpenGL glew)

find_package(OpenGL REQUIRED)
target_link_libraries(OpenGL OpenGL::GL)