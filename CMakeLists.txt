cmake_minimum_required(VERSION 3.6)

add_library(IMPLOT STATIC implot.cpp implot_items.cpp implot.h implot_internal.h)

if(MSVC)
    target_compile_options(IMPLOT PUBLIC "/ZI")
    target_link_options(IMPLOT PUBLIC "/INCREMENTAL")
    set(CMAKE_WINDOWS_EXPORT_ALL_SYMBOLS ON)

    # set(CMAKE_MSVC_RUNTIME_LIBRARY "MultiThreaded$<$<CONFIG:Debug>:Debug>")
endif()