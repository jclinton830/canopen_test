cmake_minimum_required(VERSION 3.8)
project(canopen_test)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

# find dependencies
find_package(ament_cmake REQUIRED)
find_package(lely_core_libraries REQUIRED)


generate_dcf(canopen_system)

install(DIRECTORY
  launch urdf
  DESTINATION share/${PROJECT_NAME}
)

ament_package()
