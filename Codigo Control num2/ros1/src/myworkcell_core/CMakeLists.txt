cmake_minimum_required(VERSION 2.8.3)
project(myworkcell_core)


add_compile_options(-std=c++11)


find_package(catkin REQUIRED COMPONENTS
  roscpp
  fake_ar_publisher
  geometry_msgs
  message_generation
)


add_service_files(
  FILES
  LocalizePart.srv
)


generate_messages(
  DEPENDENCIES
  geometry_msgs  # Or other packages containing msgs
)


catkin_package(

 CATKIN_DEPENDS
   roscpp
   fake_ar_publisher
   message_runtime
   geometry_msgs

)


include_directories(

  ${catkin_INCLUDE_DIRS}
)



add_executable(vision_node src/vision_node.cpp)
add_executable(myworkcell_node src/myworkcell_node.cpp)


add_dependencies(vision_node ${${PROJECT_NAME}_EXPORTED_TARGETS} ${catkin_EXPORTED_TARGETS})
add_dependencies(myworkcell_node ${${PROJECT_NAME}_EXPORTED_TARGETS} ${catkin_EXPORTED_TARGETS})

target_link_libraries(vision_node ${catkin_LIBRARIES})
target_link_libraries(myworkcell_node ${catkin_LIBRARIES})


