cmake_minimum_required(VERSION 2.8.3)
project(hear_navio_mc_example)

add_compile_options(-std=c++11)

find_package(catkin REQUIRED COMPONENTS
  roscpp
  hear_hardware_interface
  hear_architecture
  hear_ros_bridge
)

catkin_package(
  INCLUDE_DIRS
  LIBRARIES ${PROJECT_NAME}
  CATKIN_DEPENDS
    hear_ros_bridge
    roscpp
)

include_directories(
  ${catkin_INCLUDE_DIRS}
)

add_executable(mc_example_node example_node/mc_example_node.cpp)

target_link_libraries(mc_example_node ${catkin_LIBRARIES})