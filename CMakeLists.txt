project(tango)


find_package(Qt5 REQUIRED COMPONENTS Core)

SET(CMAKE_AUTORCC OFF)

qt5_add_resources(out tango.qrc )



add_library(tango ${out})
target_link_libraries(tango  Qt5::Core )


install(TARGETS tango
EXPORT tango
RUNTIME DESTINATION "${CMAKE_INSTALL_PREFIX}/bin" COMPONENT bin
LIBRARY DESTINATION "${CMAKE_INSTALL_PREFIX}/lib" COMPONENT shlib
ARCHIVE DESTINATION "${CMAKE_INSTALL_PREFIX}/lib" COMPONENT lib
)
