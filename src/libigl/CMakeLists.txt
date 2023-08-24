cmake_minimum_required(VERSION 3.0)
project(libigl)

add_library(libigl INTERFACE "D:/work/PrusaSlicer/PrusaSlicer/src/libigl")

#find_package(libigl EXACT REQUIRED PATHS "D:/work/PrusaSlicer/PrusaSlicer/src/libigl")

if(libigl_FOUND)
    message(STATUS "IGL found, using system version...")
    target_link_libraries(libigl INTERFACE igl::core)
else()
    message(STATUS "IGL NOT found, using bundled version...")
    target_include_directories(libigl SYSTEM BEFORE INTERFACE ${LIBDIR}/libigl)
endif()
