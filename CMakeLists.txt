cmake_minimum_required(VERSION 3.1)
project(game.libretro.bluemsx)

list(APPEND CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR})

find_package(Kodi REQUIRED)
find_library(BLUEMSX_LIB NAMES bluemsx_libretro${CMAKE_SHARED_LIBRARY_SUFFIX} PATH_SUFFIXES libretro)

set(BLUEMSX_CUSTOM_BINARY ${BLUEMSX_LIB}
    ${PROJECT_NAME}${CMAKE_SHARED_LIBRARY_SUFFIX})

build_addon(${PROJECT_NAME} BLUEMSX "")

include(CPack)
