#cmake_minimum_required(VERSION 3.23 FATAL_ERROR)
set( CMAKE_VERBOSE_MAKEFILE ON )

#project(RandomWalkTraditional)

IF(APPLE)
    SET(CMAKE_OSX_ARCHITECTURES "x86_64;" CACHE STRING "Build architectures for Mac OS X" FORCE)
ENDIF(APPLE)

#set(CMAKE_CXX_STANDARD 20)

get_filename_component( CINDER_PATH "~/cinder" ABSOLUTE )
get_filename_component( APP_PATH "~/Desktop/Nature_of_Code/Cinder/introduction/RandomWalkTraditional" ABSOLUTE )
get_filename_component(SOURCE_PATH "${APP_PATH}/src" ABSOLUTE)

include( "${CINDER_PATH}/proj/cmake/modules/cinderMakeApp.cmake" )

ci_make_app(
        APP_NAME    "RandomWalkTraditional"
        CINDER_PATH ${CINDER_PATH}
        SOURCES     ${SOURCE_PATH}/main.cpp ${SOURCE_PATH}/Walker.cpp
        INCLUDES    ${APP_PATH}/include
        #        RESOURCES   ${APP_PATH}/../../data/models/8lbs.obj
)
