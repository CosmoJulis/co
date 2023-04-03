cmake_minimum_required(VERSION 3.10)

project(co)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED true)

find_package(Boost 1.81 COMPONENTS program_options REQUIRED)
include_directories(${Boost_INCLUDE_DIR})

# find_package(OpenSSL)

add_executable(co main.cpp)

# target_link_libraries(co PRIVATE OpenSSL::applink)

target_link_libraries(co PRIVATE pthread)

target_link_libraries(co LINK_PUBLIC ${Boost_LIBRARIES})



