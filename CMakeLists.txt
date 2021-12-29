cmake_minimum_required(VERSION 3.21)

project(player)

list(APPEND CMAKE_MODULE_PATH ${CMAKE_CURRENT_SOURCE_DIR})

set(CMAKE_CC "g++ -std=c++11")
set(CMAKE_CFLAGS "-g -Wall")

file(GLOB SRC_FILES *.cpp)
# set(LIBS "avformat avcodec swresample swscale avutil sdl2")

find_package(SDL2 REQUIRED)
find_package(ffmpeg REQUIRED)
find_package(x264 REQUIRED)
find_package(Libswresample REQUIRED)

add_executable(player ${SRC_FILES})

target_link_libraries(player
        ${FFMPEG_LIBRARIES}
        ${SDL2_LIBRARIES}
#        ${X264_LIBS}
        ${LIBSWRESAMPLE_LIBRARIES}
        )
target_include_directories(player
        PUBLIC
        ${FFMPEG_INCLUDE_DIR}
        ${SDL2_INCLUDE_DIRS}
#        ${X264_INCLUDE_DIRS}
        ${LIBSWRESAMPLE_INCLUDE_DIRS}
        )

#target_include_directories(player PUBLIC "/usr/local/Cellar/sdl2/2.0.18/include")