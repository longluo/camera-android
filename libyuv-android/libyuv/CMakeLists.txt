cmake_minimum_required(VERSION 3.4.1)

include_directories(src/main/cpp/libyuv/include)

add_subdirectory(src/main/cpp/libyuv ./build)

aux_source_directory(src/main/cpp SRC_FILE)

add_library(yuvutil SHARED ${SRC_FILE})

find_library(log-lib log)

target_link_libraries(yuvutil ${log-lib} yuv)
