project(yolov5ncnn)
cmake_minimum_required(VERSION 3.4.1)
set(CMAKE_CXX_STANDARD 11)
set(ncnn_DIR /home/ch/d/ncnn-20210322-ubuntu-1804-shared/lib/cmake/ncnn)
#set(ncnn_DIR /home/ch/d/ncnn-20210322-full-source/build/src)


find_package(ncnn REQUIRED)

find_package(OpenCV)
include_directories(OpenCV_INCLUDE_DIRS)
add_executable(yolov5ncnn ${PROJECT_SOURCE_DIR}/main.cpp)

target_link_libraries(yolov5ncnn
        ncnn
        ${OpenCV_LIBS}
)