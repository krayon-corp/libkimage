cmake_minimum_required(VERSION 3.16.3)

project (kimg)

set (CMAKE_CXX_STANDARD 17)
set (CMAKE_C_STANDARD 17)

file(GLOB KIMG_SRC
	"src/*.h"
	"src/*.c"
	"src/*.hpp"
	"src/*.cpp"
)

add_library(kimg SHARED ${KIMG_SRC})
