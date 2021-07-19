cmake_minimum_required(VERSION 3.0.2)
project(py_trees_ros_interfaces)

find_package(catkin REQUIRED COMPONENTS
  message_generation
  std_msgs
  actionlib_msgs
  diagnostic_msgs
  geometry_msgs
  unique_identifier_msgs
)

## Generate messages in the 'msg' folder
add_message_files(
  FILES
  ActivityItem.msg
  Behaviour.msg
  BehaviourTree.msg
  KeyValue.msg
  PublisherDetails.msg
  Statistics.msg
  ServiceDetails.msg
  SnapshotStreamParameters.msg
  SubscriberDetails.msg
)

## Generate services in the 'srv' folder
add_service_files(
  FILES
  CloseBlackboardStream.srv
  CloseSnapshotStream.srv
  GetBlackboardVariables.srv
  IntrospectPublishers.srv
  IntrospectServices.srv
  IntrospectSubscribers.srv
  OpenBlackboardStream.srv
  OpenSnapshotStream.srv
  ReconfigureSnapshotStream.srv
  StatusReport.srv
)

## Generate actions in the 'action' folder
add_action_files(
  FILES
  Dock.action
  Rotate.action
  MoveBase.action
)

## Generate added messages and services with any dependencies listed here
generate_messages(
  DEPENDENCIES
  std_msgs
  actionlib_msgs
  diagnostic_msgs
  geometry_msgs
  unique_identifier_msgs
)

###################################
## catkin specific configuration ##
###################################
catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES py_trees_ros_interfaces
  CATKIN_DEPENDS message_runtime std_msgs actionlib_msgs diagnostic_msgs geometry_msgs unique_identifier_msgs
#  DEPENDS system_lib
)

###########
## Build ##
###########

include_directories(
# include
  ${catkin_INCLUDE_DIRS}
)
