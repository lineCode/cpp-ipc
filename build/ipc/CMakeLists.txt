project(ipc)

add_compile_options(-D__IPC_LIBRARY__)

include_directories(../../include ../../src)

if(UNIX)
  file(GLOB DIR_SRCS ../../src/platform/*_linux.cpp)
else()
  file(GLOB DIR_SRCS ../../src/platform/*_win.cpp)
endif()
aux_source_directory(../../src DIR_SRCS)

add_library(${PROJECT_NAME} SHARED ${DIR_SRCS})
set(LIBRARY_OUTPUT_PATH ${CMAKE_SOURCE_DIR}/../output)
