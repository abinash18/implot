cmake_minimum_required(VERSION 3.6)

add_library(IMPLOT STATIC implot.cpp implot_items.cpp implot.h implot_internal.h implot_demo.cpp)
target_link_libraries(IMPLOT PRIVATE IMGUI)

if(MSVC)
    target_compile_options(IMPLOT PUBLIC "/ZI")
    target_link_options(IMPLOT PUBLIC "/INCREMENTAL")
    set(CMAKE_WINDOWS_EXPORT_ALL_SYMBOLS ON)
    target_compile_options(IMPLOT PRIVATE /W4 /WX /arch:AVX2 /fp:fast /permissive-)

    # set(CMAKE_MSVC_RUNTIME_LIBRARY "MultiThreaded$<$<CONFIG:Debug>:Debug>")
endif()