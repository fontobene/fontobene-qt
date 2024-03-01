# CMake version configuration
cmake_minimum_required(VERSION 3.5...3.19)
if(${CMAKE_VERSION} VERSION_LESS 3.12)
    cmake_policy(VERSION ${CMAKE_MAJOR_VERSION}.${CMAKE_MINOR_VERSION})
endif()

# Define project
project(fontobene_qt
    VERSION 1.0.0
    LANGUAGES CXX
)

# Options
option(FONTOBENE_ENABLE_TESTS "Build tests for fontobene-qt." ON)

# If Qt version is not explicitly specified, automatically determine it
if(NOT FONTOBENE_QT_MAJOR_VERSION)
    find_package(Qt NAMES Qt6 Qt5 REQUIRED COMPONENTS Core)
    set(FONTOBENE_QT_MAJOR_VERSION ${Qt_VERSION_MAJOR})
endif()
set(FONTOBENE_QT "Qt${FONTOBENE_QT_MAJOR_VERSION}")

# Use C++11 (Qt5) or C++17 (Qt6)
if(FONTOBENE_QT_MAJOR_VERSION EQUAL 6)
    set(CMAKE_CXX_STANDARD 17)
else()
    set(CMAKE_CXX_STANDARD 11)
endif()
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

# Find required Qt packages
find_package(${FONTOBENE_QT} 5.2.0 REQUIRED COMPONENTS Core)
message(STATUS "Building fontobene-qt with Qt ${${FONTOBENE_QT}_VERSION}")

# Include subprojects
add_subdirectory(fontobene-qt)
if(FONTOBENE_ENABLE_TESTS)
    add_subdirectory(tests)
endif()
