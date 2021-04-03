Project(Simple-Zigbee)

set(INCLUDE_DIR "../include")

include_directories(INCLUDE_DIR)

file(GLOB SOURCES ../src/*.cpp)

add_target_library( ${Project_Name} Zigbee STATIC SOURCES)

set_target_properties(PROPERTIES Simple-Zigbee PUBLIC_HEADER)

install(TARGETS ${Project_Name}
        LIBRARY DESTINATION /usr/local/lib  
        FILES ${INCLUDE_DIR} DESTINATION /usr/local/include)