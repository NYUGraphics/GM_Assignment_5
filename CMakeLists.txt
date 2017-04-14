cmake_minimum_required(VERSION 3.1)
project(ex5)

set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} ${CMAKE_CURRENT_SOURCE_DIR}/cmake)

# libigl

option(LIBIGL_WITH_OPENGL_GLFW_IMGUI "Use ImGui"          ON)
find_package(LIBIGL REQUIRED QUIET)

# Add your project files
file(GLOB SRCFILES src/main.cpp src/Colors.cpp src/Lasso.cpp)
add_executable(${PROJECT_NAME}_bin ${SRCFILES})
target_link_libraries(${PROJECT_NAME}_bin igl::core igl::opengl_glfw igl::opengl_glfw_imgui)