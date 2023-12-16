cmake_minimum_required(VERSION 3.22)
project(image_srvs)

# Default to C++14
if(NOT CMAKE_CXX_STANDARD)
  set(CMAKE_CXX_STANDARD 17)
endif()

add_compile_options(-Wall -Wextra -Wpedantic -Wconversion -Wdouble-promotion -Wfloat-equal -Wshadow)

find_package(ament_cmake REQUIRED)
find_package(builtin_interfaces REQUIRED)
find_package(rosidl_default_generators REQUIRED)
find_package(sensor_msgs REQUIRED)

rosidl_generate_interfaces(${PROJECT_NAME}
  "srv/Grab.srv"
  "srv/Tag.srv"
  DEPENDENCIES builtin_interfaces sensor_msgs
)

ament_export_dependencies(rosidl_default_runtime)
ament_package()
