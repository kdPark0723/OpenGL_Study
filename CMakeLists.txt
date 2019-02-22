# CMake entry point
cmake_minimum_required (VERSION 3.0)
project (OpenGLStudy)

find_package(OpenGL REQUIRED)

# Compile external dependencies

set(GLFW_BUILD_DOCS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)

add_subdirectory(external)
include_directories(
	external/glfw-3.2.1/include/
	.
)
set(ALL_LIBS
	${OPENGL_LIBRARY}
	glfw
)

# chapter 1
add_executable(chapter_1
	chapter_1/firstWindow.cpp
)
target_link_libraries(chapter_1
	${ALL_LIBS}
)