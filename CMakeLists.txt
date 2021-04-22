CMAKE_MINIMUM_REQUIRED(VERSION 2.8)


# CMake used to complain without this
#if(COMMAND cmake_policy)
#  cmake_policy(SET CMP0003 NEW)
#endif(COMMAND cmake_policy)
 
SET(CMAKE_BUILD_TYPE "Debug")
SET(CMAKE_CXX_FLAGS_DEBUG "$ENV{CXXFLAGS} -O0 -Wall -g2 -ggdb")
SET(CMAKE_CXX_FLAGS_RELEASE "$ENV{CXXFLAGS} -O3 -Wall")

#SET(CMAKE_VERBOSE_MAKEFILE 1)
SET(CMAKE_CXX_FLAGS "-std=c++14 ")
ADD_DEFINITIONS( -D_STDINT_H )
add_definitions(-w)
SET(MP4 MP4_test)

INCLUDE_DIRECTORIES(
    ${CMAKE_CURRENT_SOURCE_DIR}
   
    )


SET(SRC_FILES_mp4    
	mp4.c
	mp4parser.c
	stream.c
    )


ADD_EXECUTABLE(${MP4} ${SRC_FILES_mp4})
 TARGET_LINK_LIBRARIES(${MP4} m)

