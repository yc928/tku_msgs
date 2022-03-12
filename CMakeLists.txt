cmake_minimum_required(VERSION 3.5)
project(tku_msgs)

# Default to C99
if(NOT CMAKE_C_STANDARD)
  set(CMAKE_C_STANDARD 99)
endif()

# Default to C++14
if(NOT CMAKE_CXX_STANDARD)
  set(CMAKE_CXX_STANDARD 14)
endif()

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

# find dependencies
find_package(ament_cmake REQUIRED)
# uncomment the following section in order to fill in
# further dependencies manually.
# find_package(<dependency> REQUIRED)

find_package(rosidl_default_generators REQUIRED)

rosidl_generate_interfaces(${PROJECT_NAME}
  "msg/ButtonColorForm.msg"
  "msg/HSVValue.msg"
  "msg/CameraProperty.msg"
  "msg/segmention/ColorObjects.msg"
  "msg/segmention/ObjectInfo.msg"
  "msg/segmention/ObjectList.msg"
  "msg/HeadPackage.msg"
  "msg/SensorSet.msg"
  "msg/Interface.msg"
  "msg/DrawData.msg"
  "msg/Parameter.msg"
  "msg/SensorPackage.msg"
  "msg/Walking.msg"
  "msg/SaveMotion.msg"
  "msg/SingieMotorAction.msg"
  "msg/MotorAction.msg"
  "srv/HSVInfo.srv"
  "srv/SaveHSV.srv"
  "srv/WalkingGaitParameter.srv"
  "srv/CameraPropertySrv.srv"
  "srv/ReadMotion.srv"
  "srv/ExecuteSector.srv"
 )

if(BUILD_TESTING)
  find_package(ament_lint_auto REQUIRED)
  # the following line skips the linter which checks for copyrights
  # uncomment the line when a copyright and license is not present in all source files
  #set(ament_cmake_copyright_FOUND TRUE)
  # the following line skips cpplint (only works in a git repo)
  # uncomment the line when this package is not in a git repo
  #set(ament_cmake_cpplint_FOUND TRUE)
  ament_lint_auto_find_test_dependencies()
endif()

ament_package()
