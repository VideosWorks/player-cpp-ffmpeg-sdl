cmake_minimum_required(VERSION 3.21)

project(DiscoveryPlayer)

list(APPEND CMAKE_MODULE_PATH ${CMAKE_CURRENT_SOURCE_DIR})

#set(CMAKE_CC "g++ -std=c++11")
#set(CMAKE_CFLAGS "-g -Wall")

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

file(GLOB SRC_FILES *.cpp)

# message(FATAL_ERROR ${SRC_FILES})
#list(REMOVE_ITEM SRC_FILES "${CMAKE_SOURCE_DIR}/Renderer.cpp")

find_package(SDL2 REQUIRED)
find_package(ffmpeg REQUIRED)
#find_package(x264 REQUIRED)
find_package(Libswresample REQUIRED)

list(APPEND TARGET_LIBRARIES "-framework CoreVideo")
list(APPEND TARGET_LIBRARIES "-framework Cocoa")
list(APPEND TARGET_LIBRARIES "-framework IOKit")
list(APPEND TARGET_LIBRARIES "-framework ForceFeedback")
list(APPEND TARGET_LIBRARIES "-framework Carbon")
list(APPEND TARGET_LIBRARIES "-framework CoreAudio")
list(APPEND TARGET_LIBRARIES "-framework AudioToolbox")
list(APPEND TARGET_LIBRARIES "-framework Metal")
list(APPEND TARGET_LIBRARIES "-framework OpenGL")

add_executable(${CMAKE_PROJECT_NAME} ${SRC_FILES})

target_link_libraries(${CMAKE_PROJECT_NAME}
        ${FFMPEG_LIBRARIES}
        ${SDL2_LIBRARIES}
#        ${X264_LIBS}
        ${LIBSWRESAMPLE_LIBRARIES}
        ${TARGET_LIBRARIES}
        )
target_include_directories(${CMAKE_PROJECT_NAME}
        PUBLIC
        ${FFMPEG_INCLUDE_DIR}
        ${SDL2_INCLUDE_DIRS}
#        ${X264_INCLUDE_DIRS}
        ${LIBSWRESAMPLE_INCLUDE_DIRS}
        )
