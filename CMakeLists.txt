cmake_minimum_required(VERSION 3.14)
project(sqlc)

find_package (SQLite3)

set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_FLAGS -Wall)

set(INCLUDES
        include/sqlite_orm/sqlite_orm.h)

set(SOURCES
        main.cpp)

add_executable(sqlc ${INCLUDES} ${SOURCES})

include_directories(${SQLite3_INCLUDE_DIRS})
target_link_libraries (sqlc ${SQLite3_LIBRARIES})