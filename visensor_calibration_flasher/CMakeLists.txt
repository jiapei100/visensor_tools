cmake_minimum_required(VERSION 2.8.3)
project(visensor_calibration_flasher)

find_package(catkin REQUIRED COMPONENTS
  roscpp 
  libvisensor
)

include_directories(include ${catkin_INCLUDE_DIRS})

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -march=native -Wall -std=c++0x -D__STRICT_ANSI__")

catkin_package(
  INCLUDE_DIRS ${catkin_INCLUDE_DIRS}
  CATKIN_DEPENDS
  roscpp 
  libvisensor
)

add_executable(visensor_calibration_flasher src/visensor_calibration_flasher.cpp )

target_link_libraries(visensor_calibration_flasher ${catkin_LIBRARIES})
