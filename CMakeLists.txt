cmake_minimum_required(VERSION 3.15)
project(flat_practice)

set(CMAKE_CXX_STANDARD 17)
set(EXECUTABLE_OUTPUT_PATH ${CMAKE_CURRENT_SOURCE_DIR}/bin)

find_package(gtest REQUIRED)
find_package(Threads REQUIRED)
include_directories( ${CMAKE_CURRENT_SOURCE_DIR}  ${GTEST_INCLUDE_DIRS} )
enable_testing()
add_executable(Test main_test.cpp)

add_test(Test ${PROJECT_SOURCE_DIR}/bin/testing)

add_executable(flat_practice main.cpp)

add_library(EarleyParser SHARED
        src/EarleyParser.cpp
        src/Grammar.cpp
        src/GrammarRule.cpp
        include/EarleyParser.h
        include/Grammar.h
        include/GrammarRule.h
        )

target_link_libraries(flat_practice EarleyParser)

target_link_libraries(Test EarleyParser)
target_link_libraries(Test Threads::Threads ${GTEST_LIBRARIES} ${GMOCK_BOTH_LIBRARIES})
