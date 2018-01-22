cmake_minimum_required(VERSION 2.8.3)
project(knowledge_msgs)

find_package(catkin REQUIRED COMPONENTS
  message_generation
  std_msgs
  geometry_msgs
)

add_message_files(FILES TrainingData.msg PerceivedObject.msg)

add_service_files(FILES GetFixedKitchenObjects.srv Classify.srv)

generate_messages(
  DEPENDENCIES
  std_msgs
  geometry_msgs
)

catkin_package(CATKIN_DEPENDS 
  message_runtime 
  std_msgs 
  geometry_msgs
)

include_directories(
  ${catkin_INCLUDE_DIRS}
)