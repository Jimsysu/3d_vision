cmake_minimum_required(VERSION 3.1)
project(gps_vis_odom)
add_definitions(--std=c++11 -Wno-unknown-pragmas -w)

find_package(catkin_simple REQUIRED)
catkin_simple(ALL_DEPS_REQUIRED)
cs_add_library(${PROJECT_NAME}
    src/CoorConv.cpp
)
cs_add_executable(${PROJECT_NAME}_test
    src/main.cc
)
target_link_libraries(${PROJECT_NAME}_test ${PROJECT_NAME})

cs_install()
cs_export()

