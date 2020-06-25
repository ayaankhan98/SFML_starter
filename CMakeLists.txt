cmake_minimum_required(VERSION 3.16.8)

project(test)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)

set(SFML_INCLUDE_DIR "${CMAKE_CURRENT_SOURCE_DIR}/libraries/SFML/include")
set(SFML_LIBRARY_DIR "${CMAKE_CURRENT_SOURCE_DIR}/libraries/SFML/lib")
set(SFML_DIR "${CMAKE_CURRENT_SOURCE_DIR}/libraries/SFML/lib/cmake/SFML")

link_directories(SFML_LIBRARY_DIR)
include_directories(SFML_INCLUDE_DIR)

find_package(SFML 2.5.1 COMPONENTS system window graphics network audio)

if(SFML_FOUND)
    message(STATUS "SFML_INCLUDE_DIR: ${SFML_INCLUDE_DIR}")
    message(STATUS "SFML_LIBRARIES: ${SFML_LIBRARIES}")
    message(STATUS "SFML_VERSION: ${SFML_VERSION}")
endif()

add_executable(test main.cpp)
target_link_libraries (test sfml-graphics sfml-window sfml-system sfml-audio sfml-network)