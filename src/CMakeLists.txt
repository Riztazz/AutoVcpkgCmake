set( TARGET_NAME AutoVcpkgProjectTest )

find_package(fmt CONFIG REQUIRED)
add_executable( ${TARGET_NAME} )

target_include_directories( ${TARGET_NAME}
    PUBLIC
        ${CMAKE_CURRENT_SOURCE_DIR}
)

file( GLOB_RECURSE TARGET_SOURCES CONFIGURE_DEPENDS *.cpp *.hpp *.h )

set( TARGET_SOURCES ${TARGET_SOURCES} )

target_sources( ${TARGET_NAME}
    PRIVATE
        ${TARGET_SOURCES} )

source_group(TREE "${CMAKE_CURRENT_SOURCE_DIR}" FILES ${TARGET_SOURCES})

target_link_libraries( ${TARGET_NAME}
    PUBLIC
        fmt::fmt )

