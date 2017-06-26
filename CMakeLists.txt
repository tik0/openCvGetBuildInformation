cmake_minimum_required (VERSION 2.6)
PROJECT("openCvBuildInformation")
MESSAGE(STATUS "INFO:
  If you want to change the OpenCV installation path,
  you'll have to proivde the folder which contains
  'OpenCVConfig.cmake' via the 'OpenCV_DIR' variable. E.g.:
  $ cmake -DOpenCV_DIR=/usr/local/share/OpenCV .")
FIND_PACKAGE(OpenCV REQUIRED)
INCLUDE_DIRECTORIES (include ${OpenCV_INCLUDE_DIRS})
ADD_EXECUTABLE ("${PROJECT_NAME}" main.cxx)
TARGET_LINK_LIBRARIES ("${PROJECT_NAME}" ${OpenCV_LIBRARIES})
SET ( CMAKE_CXX_FLAGS_DEBUG "-O0 -g" )
SET ( CMAKE_CXX_FLAGS_RELEASE "-O2" )
ADD_DEFINITIONS(-std=c++11 -Wall -Wno-deprecated-declarations)
