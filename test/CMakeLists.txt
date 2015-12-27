cmake_minimum_required (VERSION 2.6)

find_package (Boost COMPONENTS system filesystem unit_test_framework REQUIRED)

set(TEST_SOURCE_DIR ${CMAKE_CURRENT_SOURCE_DIR}/src)

include_directories (${TEST_SOURCE_DIR}
                     ${APPLICATION_INCLUDE_DIR}
                     ${Boost_INCLUDE_DIRS}
                     )

file(GLOB TEST_SOURCES
    ${TEST_SOURCE_DIR}/*.cpp
)

add_definitions (-DBOOST_TEST_DYN_LINK)
add_executable (test-app
                ${TEST_SOURCES}
                ${APPLICATION_SOURCES_WITHOUT_MAIN})

target_link_libraries (test-app
                       ${Boost_FILESYSTEM_LIBRARY}
                       ${Boost_SYSTEM_LIBRARY}
                       ${Boost_UNIT_TEST_FRAMEWORK_LIBRARY}
                       )
