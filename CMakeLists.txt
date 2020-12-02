cmake_minimum_required (VERSION 3.0)
project (OpenOCD)

#set(CMAKE_VERBOSE_MAKEFILE ON)

INCLUDE (CheckIncludeFiles)
SET(OPENOCD_VERSION 0.10.0)

if (WIN32)
set(SH_WRAPPER ${CMAKE_CURRENT_SOURCE_DIR}/external/run-sh.bat)
endif()
if(UNIX)
    set(SH_WRAPPER "/bin/sh")
endif()

include(config.cmake)

#add_subdirectory(external/hidapi/scripts)
#add_subdirectory(external/libusb1/scripts)
#add_subdirectory(external/prebuilt)

add_definitions(-DHAVE_CONFIG_H -DPKGDATADIR="../../share/openocd" -DBINDIR="../../bin" -D__USE_MINGW_ANSI_STDIO=1)
include_directories(${CMAKE_CURRENT_BINARY_DIR} ${LIBUSB1_INCLUDE_DIR} ${HIDAPI_INCLUDE_DIR})
set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -std=gnu99 -Werror=incompatible-pointer-types")

add_subdirectory(jimtcl)
add_subdirectory(src)

INSTALL(DIRECTORY tcl/ DESTINATION share/openocd/scripts)
INSTALL(DIRECTORY contrib DESTINATION share/openocd)
