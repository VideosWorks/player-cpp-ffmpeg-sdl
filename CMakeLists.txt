cmake_minimum_required(VERSION 3.21)

project(DiscoveryPlayer)

list(APPEND CMAKE_MODULE_PATH ${CMAKE_CURRENT_SOURCE_DIR})

set(CMAKE_CC "g++ -std=c++11")
set(CMAKE_CFLAGS "-g -Wall")

file(GLOB SRC_FILES *.cpp)

#message(FATAL_ERROR ${SRC_FILES})
file(REMOVE ${SRCE_FILES} "WorldDebugDrawer.cpp" "Renderer.cpp")

find_package(SDL2 REQUIRED)
find_package(ffmpeg REQUIRED)
find_package(x264 REQUIRED)
find_package(Libswresample REQUIRED)

add_executable(${CMAKE_PROJECT_NAME} ${SRC_FILES})

target_link_libraries(${CMAKE_PROJECT_NAME}
        ${FFMPEG_LIBRARIES}
        ${SDL2_LIBRARIES}
#        ${X264_LIBS}
        ${LIBSWRESAMPLE_LIBRARIES}
        )
target_include_directories(${CMAKE_PROJECT_NAME}
        PUBLIC
        ${FFMPEG_INCLUDE_DIR}
        ${SDL2_INCLUDE_DIRS}
#        ${X264_INCLUDE_DIRS}
        ${LIBSWRESAMPLE_INCLUDE_DIRS}
        )
