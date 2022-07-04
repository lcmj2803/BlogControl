cmake_minimum_required(VERSION 2.8.3)
project(myworkcell_core)

add_compile_options(-std=c++11)

find_package(catkin REQUIRED COMPONENTS
  roscpp
  fake_ar_publisher
)
catkin_package(

 CATKIN_DEPENDS
   roscpp
   fake_ar_publisher
)



include_directories(

  ${catkin_INCLUDE_DIRS}
)


