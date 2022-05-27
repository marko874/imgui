cmake_minimum_required(VERSION 3.8)
project(imgui)
find_package(Vulkan REQUIRED)

add_library(imgui 
 imconfig.h
 imgui_demo.cpp
 imgui_draw.cpp
 imgui_internal.h
 imgui_tables.cpp
 imgui_widgets.cpp
 imgui.cpp
 imgui.h
 imstb_rectpack.h
 imstb_textedit.h
 imstb_truetype.h

 backends/imgui_impl_glfw.cpp
 backends/imgui_impl_glfw.h
 backends/imgui_impl_vulkan.cpp
 backends/imgui_impl_vulkan.h
)

target_include_directories(imgui PUBLIC ${Vulkan_INCLUDE_DIRS})
target_link_libraries(imgui PUBLIC ${Vulkan_LIBRARIES})