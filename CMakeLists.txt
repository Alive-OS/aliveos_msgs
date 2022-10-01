cmake_minimum_required(VERSION 3.5)
project (aliveos_msgs)

find_package(ament_cmake REQUIRED)
find_package(builtin_interfaces  REQUIRED)
find_package(rosidl_default_generators REQUIRED)


set(msg_files
    "msg/DeviceCmd.msg"
    "msg/DeviceData.msg"
    "msg/EgoCommands.msg"
    "msg/EmotionParams.msg"
    "msg/PerceptionConcept.msg"
)

set(srv_files
    "srv/CommandConcept.srv"
    "srv/CommandConceptDescriptor.srv"
    "srv/EmotionCoreDataDescriptor.srv"
    "srv/EmotionCoreWrite.srv"
    "srv/Hw.srv"
    "srv/PerceptionConceptDescriptor.srv"
)

rosidl_generate_interfaces(${PROJECT_NAME}
    ${msg_files}
    ${srv_files}
    DEPENDENCIES builtin_interfaces)

ament_package()
