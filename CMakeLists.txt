cmake_minimum_required(VERSION 2.8)
PROJECT (keypoints)
set (CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -std=c++11")
find_package(OpenCV REQUIRED )
set( NAME_SRC
    src/laser_scan.cpp
)

set( NAME_HEADERS
     include/FileReader.h
     include/GrayFileReader.h
     include/GrayValues.h
     include/RowCol.h
     include/RowColReader.h
     include/Values.h
)

INCLUDE_DIRECTORIES( ${CMAKE_CURRENT_SOURCE_DIR}/include ${CMAKE_CURRENT_SOURCE_DIR}/src )
add_executable( keypoints ${NAME_SRC} ${NAME_HEADERS} )
target_link_libraries( keypoints ${OpenCV_LIBS} )
