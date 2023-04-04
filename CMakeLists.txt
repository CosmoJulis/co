cmake_minimum_required(VERSION 3.10)

project(co)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED true)




find_package(Boost 1.81 COMPONENTS thread REQUIRED)
include_directories(${Boost_INCLUDE_DIR})

find_package(OpenSSL)
include_directories(${OPENSSL_INCLUDE_DIRS})

set(SERVER "ws_server")
set(CLIENT "ws_client")

add_executable(${SERVER} ws_server.cpp)
add_executable(${CLIENT} ws_client.cpp)

target_link_libraries(${SERVER} LINK_PUBLIC ${Boost_LIBRARIES})
target_link_libraries(${SERVER} LINK_PUBLIC ${OPENSSL_LIBRARIES})

target_link_libraries(${CLIENT} LINK_PUBLIC ${Boost_LIBRARIES})
target_link_libraries(${CLIENT} LINK_PUBLIC ${OPENSSL_LIBRARIES})

