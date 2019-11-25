cmake_minimum_required(VERSION 3.5)

project(RS-PCL LANGUAGES CXX)

set(CMAKE_INCLUDE_CURRENT_DIR ON)

set(CMAKE_AUTOUIC ON)
set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)

set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(Qt5 COMPONENTS Widgets REQUIRED)
find_package(realsense2 REQUIRED)
find_package(PCL 1.9 REQUIRED COMPONENTS segmentation io visualization)

add_executable(RS-PCL
  main.cpp
  mainwindow.cpp
  mainwindow.h
  mainwindow.ui
)

target_link_libraries(RS-PCL PRIVATE
    Qt5::Widgets
    ${realsense2_LIBRARY}
    ${PCL_LIBRARIES}
    )
