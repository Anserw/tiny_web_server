PROJECT(tiny_web_server)
cmake_minimum_required(VERSION 2.8)


INCLUDE_DIRECTORIES(
	include
)

AUX_SOURCE_DIRECTORY(src DIR_SRCS)

SET(TINY_WEB_SERVER
	${DIR_SRCS}
)

SET(LIBRARIES
	libpthread.so
)

ADD_LIBRARY(csapp ./src/csapp.c)

ADD_EXECUTABLE(./bin/tiny_web_server ${TINY_WEB_SERVER})

TARGET_LINK_LIBRARIES(./bin/tiny_web_server csapp ${LIBRARIES})
