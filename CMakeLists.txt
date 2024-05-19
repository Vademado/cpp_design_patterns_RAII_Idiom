cmake_minimum_required(VERSION 3.4)
project(RAII_Idiom_Project)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
option(BUILD_TESTS "Build tests" OFF)

if(BUILD_TESTS)
    include_directories(.)
    add_library(dummy STATIC Dummy.h Dummy.cpp)
    enable_testing()
    add_subdirectory(third-party/gtest)
    file(GLOB tests "tests/*.cpp")
    foreach(test ${tests})
         add_executable(check ${test})
         target_link_libraries(check gtest_main gmock_main dummy)
         add_test(NAME check COMMAND check)
    endforeach(test ${tests})
else()
    set(SOURCES
        Clipboard.cpp
        ConceptualExample.cpp
        Dummy.cpp
        Program.cpp
        RAII_File.cpp
        RAII_Ofstream.cpp
    )
    add_executable(RAII_Idiom_Project ${SOURCES})
endif()
