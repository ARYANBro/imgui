project(imgui)

set(SourceFiles
    imgui_demo.cpp
    imgui_draw.cpp
    imgui_tables.cpp
    imgui_widgets.cpp
    imgui.cpp
    backends/imgui_impl_opengl3.cpp
    backends/imgui_impl_glfw.cpp
)

add_library(${PROJECT_NAME} STATIC ${SourceFiles})

target_include_directories(${PROJECT_NAME}
    PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}
)

target_link_libraries(${PROJECT_NAME}
    glfw
    glad
)

add_compile_definitions(
    IMGUI_IMPL_OPENGL_LOADER_GLAD
)

add_compile_options(
    -Wall
    -Wformat
)
