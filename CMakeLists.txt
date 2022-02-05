cmake_minimum_required(VERSION 3.3)
project(openGL_tutorial)
find_package(OpenGL REQUIRED)
if(NOT OPENGL_FOUND)
    message("ERROR: OpenGL not found")
endif(NOT OPENGL_FOUND)
set(GL_LIBRARY GL GLU X11)

add_executable(t main.cpp
        imgui/imgui.cpp
        imgui/imgui_demo.cpp
        imgui/imgui_draw.cpp
        imgui/imgui_tables.cpp
        imgui/imgui_widgets.cpp
        imgui/backends/imgui_impl_glfw.cpp
        imgui/backends/imgui_impl_opengl3.cpp
        )
target_include_directories(t PUBLIC imgui .)

target_link_libraries(t dl glfw GL m GLEW glfw GLEW libGLEW.so libGLU.so libGL.so)