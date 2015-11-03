cmake_minimum_required(VERSION 2.8.3)
project(image_converter)

find_package(catkin REQUIRED COMPONENTS
    cv_bridge
    image_transport
    roscpp
    sensor_msgs
    std_msgs
)

find_package(OpenCV REQUIRED COMPONENTS
    imgproc
    highgui
)

###########
## Build ##
###########

include_directories(
    ${catkin_INCLUDE_DIRS}
)

add_executable(image_converter_node src/image_converter.cpp)

target_link_libraries(image_converter_node
    ${catkin_LIBRARIES}
    ${OpenCV_LIBS}
)

