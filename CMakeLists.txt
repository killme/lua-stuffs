cmake_minimum_required(VERSION 2.6)
cmake_policy(SET CMP0012 NEW)
project(lua-stuffs)

set(BUILD_TEMP_DIR         ${CMAKE_BINARY_DIR}/tmp)
set(BUILD_TEMP_INCLUDE_DIR ${BUILD_TEMP_DIR}/include)
file(MAKE_DIRECTORY       ${BUILD_TEMP_DIR})
file(MAKE_DIRECTORY       ${BUILD_TEMP_INCLUDE_DIR})

set(BUILD_SHARED_DIR "${CMAKE_INSTALL_PREFIX}/share/lua-stuffs")

set(BUILD_INSTALL_BIN_DIR "${CMAKE_INSTALL_PREFIX}/bin")
set(BUILD_INSTALL_LIB_DIR "${CMAKE_INSTALL_PREFIX}/lib")

set(CMAKE_CURRENT_BINARY_DIR ${BUILD_INSTALL_BIN_DIR})
set(INSTALL_HEADER_DIR      ${BUILD_TEMP_INCLUDE_DIR}   CACHE INTERNAL "")

set(INSTALL_LIBRARY_DIR     ${BUILD_INSTALL_LIB_DIR}    CACHE INTERNAL "")
set(INSTALL_ARCHIVE_DIR     ${BUILD_INSTALL_LIB_DIR}    CACHE INTERNAL "")

set(INSTALL_RUNTIME_DIR     ${BUILD_INSTALL_BIN_DIR}    CACHE INTERNAL "")
set(INSTALL_DOC_DIR         ${BUILD_SHARED_DIR}/docs    CACHE INTERNAL "")

set(INSTALL_RESOURCES_DIR   ${BUILD_SHARED_DIR}  CACHE INTERNAL "")
set(INSTALL_LUA_DIR         ${BUILD_SHARED_DIR}/lua  CACHE INTERNAL "")

message(STATUS "Installing to ${BUILD_INSTALL_DIR} (bin: ${CMAKE_CURRENT_BINARY_DIR}, resources: ${INSTALL_RESOURCES_DIR}, header: ${INSTALL_HEADER_DIR}")

add_subdirectory(libraries/yajl)
add_subdirectory(libraries/http-parser)
add_subdirectory(libraries/libuv)
add_subdirectory(libraries/OpenDBX-uv)
add_subdirectory(libraries/OpenDBX-uv-lua)
add_subdirectory(libraries/luvit)
add_subdirectory(libraries/Luapp)
