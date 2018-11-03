project(tango-icon-theme)


find_package(Qt5 REQUIRED COMPONENTS Core)

SET(CMAKE_AUTORCC OFF)

qt5_add_resources(out tango-icon-theme.qrc )



add_library(tango-icon-theme ${out})
target_link_libraries(tango-icon-theme  Qt5::Core )


install(TARGETS tango-icon-theme
EXPORT tango-icon-theme
RUNTIME DESTINATION "${CMAKE_INSTALL_PREFIX}/bin" COMPONENT bin
LIBRARY DESTINATION "${CMAKE_INSTALL_PREFIX}/lib" COMPONENT shlib
ARCHIVE DESTINATION "${CMAKE_INSTALL_PREFIX}/lib" COMPONENT lib
)
