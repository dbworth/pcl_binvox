cmake_minimum_required(VERSION 2.8.3)
project(pcl_binvox)

# Use C++ 11
if(CMAKE_COMPILER_IS_GNUCXX)
  add_definitions("-std=c++11")
endif()

find_package(catkin REQUIRED COMPONENTS
  cmake_modules
  pcl_ros          # pcl_ros must appear before pcl_conversions
  pcl_conversions  # or the wrong headers are used.
)

find_package(PCL 1.6 REQUIRED)

catkin_package(
  INCLUDE_DIRS ${catkin_INCLUDE_DIRS} #include 
  LIBRARIES ${PROJECT_NAME}
  #DEPENDS
)

include_directories(
  #include
  ${INCLUDE_DIRECTORIES}
  ${catkin_INCLUDE_DIRS}
  ${PCL_INCLUDE_DIRS})

link_directories(${LINK_DIRECTORIES} ${PCL_LIBRARY_DIRS})

add_definitions(${PCL_DEFINITIONS})

add_executable(binvox2pcd src/binvox2pcd.cpp)
target_link_libraries(binvox2pcd ${catkin_LIBRARIES})

add_executable(pcd2binvox src/pcd2binvox.cpp)
target_link_libraries(pcd2binvox ${catkin_LIBRARIES})
