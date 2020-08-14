cmake_minimum_required(VERSION 2.8.3)
project(multi_slam_karto)

find_package(Boost REQUIRED COMPONENTS thread)
find_package(catkin REQUIRED
  COMPONENTS
    cmake_modules
    message_filters
    nav_msgs
#    open_karto
    laser_geometry
    rosconsole
    roscpp
    rospy
    sensor_msgs
    sparse_bundle_adjustment
    tf
    visualization_msgs
    std_msgs
)
# include_directories("/usr/local/include/eigen3")
include_directories(${PROJECT_SOURCE_DIR}/src)
find_package(Eigen REQUIRED)

include_directories(${catkin_INCLUDE_DIRS})
add_definitions(${EIGEN_DEFINITIONS})

catkin_package()

add_executable(multi_slam_karto src/slam_karto.cpp src/spa_solver.cpp src/Karto.cpp src/Mapper.cpp)
target_link_libraries(multi_slam_karto ${catkin_LIBRARIES})

# install(TARGETS multi_slam_karto
#   RUNTIME DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
# )
