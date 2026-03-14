cmake_minimum_required(VERSION 3.5)
project(vmo_locomotion_interface)

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
find_package(geometry_msgs REQUIRED)
find_package(rosidl_default_generators REQUIRED)

rosidl_generate_interfaces(${PROJECT_NAME}
	"msg/IMUState.msg"
	"msg/LowCmd.msg"
	"msg/LowState.msg"
	"msg/MotorCmd.msg"
	"msg/JointCmd.msg"
	"msg/JointCmds.msg"
  	"msg/MotorCmds.msg"
	"msg/MotorState.msg"
	"msg/JointState.msg"
	"msg/JointStates.msg"
	"msg/MotorStates.msg"
	"msg/FSMState.msg"
	"msg/FSMCmd.msg"
	"msg/RobotState.msg"
	"msg/UpperBodyRequest.msg"
  DEPENDENCIES geometry_msgs
)

ament_package()
