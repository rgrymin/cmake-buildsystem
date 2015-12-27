cmake_minimum_required (VERSION 2.6)
project(APPLICATION CXX)

include_directories(${APPLICATION_INCLUDE_DIR}
                    ${RAPIDXML_INCLUDE_DIR})
add_executable(app ${APPLICATION_SOURCES})
