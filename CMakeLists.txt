cmake_minimum_required(VERSION 2.8.3)
project(scout_ndirect)

find_package(catkin REQUIRED COMPONENTS
  roscpp
  sensor_msgs
  geometry_msgs
  nav_msgs
  tf
)


catkin_package(
   INCLUDE_DIRS include
)

include_directories(include
  ${catkin_INCLUDE_DIRS}
)

add_executable(scout_node src/scout_node.cpp src/Ndirect/Ndirect.c)

target_link_libraries(scout_node
   ${catkin_LIBRARIES}
)


install(TARGETS scout_node
   ARCHIVE DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
   LIBRARY DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
   RUNTIME DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)

