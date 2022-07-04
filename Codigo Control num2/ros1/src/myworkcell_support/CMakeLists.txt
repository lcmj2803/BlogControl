cmake_minimum_required(VERSION 2.8.3)
project(myworkcell_support)

find_package(catkin REQUIRED COMPONENTS
  myworkcell_core
)



include_directories(

  ${catkin_INCLUDE_DIRS}
)


