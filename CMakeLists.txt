cmake_minimum_required(VERSION 2.8)

project(bbbiommap)

file( GLOB BBBIO_SOURCES BBBio_lib/*.c )
file( GLOB BBBIO_HEADERS BBBio_lib/*.h )

set(folder_source ${BBBIO_SOURCES})
set(folder_header ${BBBIO_HEADERS})
source_group("Source Files" FILES ${folder_source})
source_group("Header Files" FILES ${folder_header})

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/BBBio_lib)

add_library(bbbiommap ${folder_source})

# set_target_properties(bbbiommap PROPERTIES LINKER_LANGUAGE C)

install(TARGETS bbbiommap DESTINATION bin/)
