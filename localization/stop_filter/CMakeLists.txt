cmake_minimum_required(VERSION 3.14)
project(stop_filter)

find_package(autoware_cmake REQUIRED)
autoware_package()

ament_auto_add_library(${PROJECT_NAME} SHARED
  src/stop_filter.cpp
)

rclcpp_components_register_node(${PROJECT_NAME}
  PLUGIN "StopFilter"
  EXECUTABLE ${PROJECT_NAME}_node
  EXECUTOR SingleThreadedExecutor
)

ament_auto_package(
  INSTALL_TO_SHARE
  launch
  config
)
