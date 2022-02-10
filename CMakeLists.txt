cmake_minimum_required(VERSION 3.16)
project(tango-icon-theme)


find_package(Qt6 REQUIRED COMPONENTS Core)

SET(CMAKE_AUTORCC OFF)

qt6_add_resources(out tango.qrc )


if (WIN32)
    add_library(tango-icon-theme ${out} tango-icon-schemeW32.cpp)
else()
    add_library(tango-icon-theme ${out})
endif()

target_link_libraries(tango-icon-theme  Qt6::Core )


install(TARGETS tango-icon-theme
EXPORT tango-icon-theme
RUNTIME DESTINATION "${CMAKE_INSTALL_PREFIX}/bin" COMPONENT bin
LIBRARY DESTINATION "${CMAKE_INSTALL_PREFIX}/lib" COMPONENT shlib
ARCHIVE DESTINATION "${CMAKE_INSTALL_PREFIX}/lib" COMPONENT lib
)
