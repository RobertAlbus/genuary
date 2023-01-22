########
# Clover: Composable Signal Graphs for Creative Sound Coding

cmake_minimum_required(VERSION 3.14)
project(Genuary)

########
# Clover variables

set(CLOVER_BUILD_DEMO OFF)
set(CLOVER_BUILD_TESTS OFF)
set(BUILD_GENUARY_23 ON)


########
# cmake variables

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++20")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Ofast -lprofiler")


# Clover
add_subdirectory(dependencies/clover)
include_directories(dependencies/clover/includes)


if(BUILD_GENUARY_23)
    # j1
    add_executable(2023_1 src/2023/j1.cpp)
    target_link_libraries(2023_1 PUBLIC Clover)

    # j2
    add_executable(2023_2 src/2023/j2.cpp)
    target_link_libraries(2023_2 PUBLIC Clover)

    # j4
    add_executable(2023_4 src/2023/j4.cpp)
    target_link_libraries(2023_4 PUBLIC Clover)
    
    # j23
    add_executable(2023_23 src/2023/j23.cpp)
    target_link_libraries(2023_23 PUBLIC Clover)
endif()
