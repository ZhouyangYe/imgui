cmake_minimum_required(VERSION 3.20.2)
project(imgui)

add_library(${PROJECT_NAME}
  imgui.h
  imgui.cpp
  backends/imgui_impl_opengl3.h
  backends/imgui_impl_opengl3.cpp
  backends/imgui_impl_glfw.h
  backends/imgui_impl_glfw.cpp
)

target_include_directories(${PROJECT_NAME}
  PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}
  PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/backends
)
target_link_directories(${PROJECT_NAME} PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})

target_link_libraries(${PROJECT_NAME}
  glfw
  GLAD
)
