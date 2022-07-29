cmake_minimum_required(VERSION 3.16.3)

project (kimg)

set (CMAKE_CXX_STANDARD 17)
set (CMAKE_C_STANDARD 17)
set (CMAKE_EXPORT_COMPILE_COMMANDS ON)

file(GLOB KIMG_SRC
	"src/*.h"
	"src/*.c"
	"src/*.hpp"
	"src/*.cpp"
)

add_library(kimg SHARED ${KIMG_SRC})

# Coc
add_custom_command(
	TARGET kimg POST_BUILD
	COMMAND ${CMAKE_COMMAND} -E copy
		${CMAKE_BINARY_DIR}/compile_commands.json
		${CMAKE_SOURCE_DIR}/compile_commands.json
)
