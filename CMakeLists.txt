cmake_minimum_required(VERSION 2.8)

set(SOURCES
    "src/usb-reset.cpp"
)

add_executable(usb-reset ${SOURCES})
target_link_libraries(usb-reset usb-1.0)

install(TARGETS usb-reset
        RUNTIME DESTINATION bin)

add_custom_target(format clang-format -i ${SOURCES}
    WORKING_DIRECTORY ${CMAKE_SOURCE_DIR})
