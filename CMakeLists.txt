cmake_minimum_required(VERSION 3.4)
project(RAII_Idiom_Project)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(SOURCES
    Clipboard.cpp
    ConceptualExample.cpp
    Dummy.cpp
    Program.cpp
    RAII_File.cpp
    RAII_Ofstream.cpp
)

add_executable(RAII_Idiom_Project ${SOURCES})
