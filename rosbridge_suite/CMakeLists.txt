cmake_minimum_required(VERSION 3.5)
project(rosbridge_suite NONE)

find_package(carma_cmake_common REQUIRED)
carma_check_ros_version(2)

find_package(ament_cmake_core REQUIRED)
ament_package()
