cmake_minimum_required(VERSION 3.17)
project(ales)

set(CMAKE_CXX_STANDARD 17)

set(BOOST_ROOT /usr/include/boost)
set(Boost_USE_STATIC_LIBS ON)
find_package(Boost COMPONENTS system thread)

include_directories(${Boost_INCLUDE_DIR})

add_executable(server Server.cpp)
target_link_libraries(server ${Boost_LIBRARIES})

add_executable(client Client.cpp)
target_link_libraries(client ${Boost_LIBRARIES})