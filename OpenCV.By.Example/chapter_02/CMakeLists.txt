cmake_minimum_required (VERSION 2.6)

cmake_policy(SET CMP0012 NEW)

PROJECT(Chapter2)

# Requires OpenCV
#FIND_PACKAGE( OpenCV 3.0.0 REQUIRED )
FIND_PACKAGE( OpenCV REQUIRED )
MESSAGE("OpenCV version : ${OpenCV_VERSION}")

include_directories(${OpenCV_INCLUDE_DIRS})
link_directories(${OpenCV_LIB_DIR})


ADD_EXECUTABLE( sample1 sample1.cpp )
TARGET_LINK_LIBRARIES( sample1 ${OpenCV_LIBS} )


ADD_EXECUTABLE( sample2 sample2.cpp )
TARGET_LINK_LIBRARIES( sample2 ${OpenCV_LIBS} )

ADD_EXECUTABLE( sample3 sample3.cpp )
TARGET_LINK_LIBRARIES( sample3 ${OpenCV_LIBS} )

ADD_EXECUTABLE( ${PROJECT_NAME} main.cpp )
TARGET_LINK_LIBRARIES( ${PROJECT_NAME} ${OpenCV_LIBS} )
