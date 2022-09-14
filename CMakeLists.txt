cmake_minimum_required(VERSION 3.14)
project(Libre-Spice)

# Add wxWidgets library
find_package(wxWidgets REQUIRED net gl core base)
include(${wxWidgets_USE_FILE})

# Fix HiDPI problems
add_compile_options(-DwxUSE_DPI_AWARE_MANIFEST=2)

# Add source files
set(
    SRC_FILES 
    src/main.cpp
    src/wx.rc
   )

# Disable make vebose
set(CMAKE_VERBOSE_MAKEFILE OFF)

# Export compile commands
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

add_executable(${PROJECT_NAME} ${SRC_FILES})
target_link_libraries(${PROJECT_NAME} ${wxWidgets_LIBRARIES})
