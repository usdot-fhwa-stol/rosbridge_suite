cmake_minimum_required(VERSION 3.5)
project(rosbridge_library)

find_package(carma_cmake_common REQUIRED)
carma_check_ros_version(2)

find_package(ament_cmake_ros REQUIRED)
find_package(ament_cmake_core REQUIRED)
find_package(ament_cmake_python REQUIRED)

ament_python_install_package(
  ${PROJECT_NAME} PACKAGE_DIR "src/${PROJECT_NAME}")

ament_package()

if (BUILD_TESTING)
  find_package(ament_cmake_pytest REQUIRED)

  # TODO: Enable tests
  # ament_add_pytest_test(test_capabilities "test/capabilities")
  # ament_add_pytest_test(test_internal "test/internal")
  # ament_add_pytest_test(test_services "test/internal/test_services.py")
  ament_add_pytest_test(test_ros_loader "test/internal/test_ros_loader.py")
  ament_add_pytest_test(test_message_conversion "test/internal/test_message_conversion.py")
endif()
