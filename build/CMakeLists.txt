cmake_minimum_required(VERSION 3.19)

project(Simple-Zigbee)

file(GLOB INCLUDES ../include/*.h)
file(GLOB SOURCES ../src/*.cpp)

include_directories(../include /usr/local/include)

set(CMAKE_LIBRARY_PATH ../lib)
add_library(Zigbee ${SOURCES})

target_link_libraries(Zigbee "/usr/local/include/CppLinuxSerial.a")

install(TARGETS Zigbee DESTINATION "/usr/local/lib")

install(FILES ${INCLUDES} DESTINATION /usr/local/include)
