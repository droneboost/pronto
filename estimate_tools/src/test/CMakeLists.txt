set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++0x -Wno-deprecated-declarations")

cmake_minimum_required(VERSION 2.8 FATAL_ERROR)
#project(kalman_filter_tools)

################
# Joint Level Filters
add_executable(se-kalman-filter-demo kalman_filter_demo.cpp )
pods_use_pkg_config_packages(se-kalman-filter-demo 
    path-util filter_tools kalman_filter_tools backlash_filter_tools )
# bot2-frames_cpp   pronto_vis  )
target_link_libraries (se-kalman-filter-demo lcm )
#pronto_math  )
pods_install_executables(se-kalman-filter-demo )




################
# Accel Filters
add_executable(se-filtering-demo filtering_demo.cpp)
pods_use_pkg_config_packages(se-filtering-demo 
    path-util filter_tools estimate_tools lcmtypes_bot2-core)
target_link_libraries (se-filtering-demo lcm)
pods_install_executables(se-filtering-demo)
