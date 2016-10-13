cmake_minimum_required(VERSION 2.8)
project(cocaine_io_util_precise)

add_subdirectory(cocaine-core EXCLUDE_FROM_ALL)

add_custom_target(cocaine-io-util-stub ALL DEPENDS cocaine-io-util)

INSTALL(FILES
        ${CMAKE_CURRENT_BINARY_DIR}/cocaine-core/libcocaine-io-util${CMAKE_SHARED_LIBRARY_SUFFIX}
        ${CMAKE_CURRENT_BINARY_DIR}/cocaine-core/libcocaine-io-util${CMAKE_SHARED_LIBRARY_SUFFIX}.3
        DESTINATION lib
        COMPONENT runtime)

INSTALL(
        DIRECTORY
        cocaine-core/include/
        DESTINATION include
        COMPONENT development
        PATTERN "detail" EXCLUDE)

install(
        DIRECTORY
            cocaine-plugins/node/include/cocaine/api
            cocaine-plugins/node/include/cocaine/idl
            cocaine-plugins/node/include/cocaine/service
        DESTINATION include/cocaine-node
        COMPONENT development)


