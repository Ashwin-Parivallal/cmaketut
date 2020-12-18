cmake_minimum_required(VERSION 3.16.3)

project(httpreq)

add_executable(${PROJECT_NAME} main.cpp)

#build these subdirectories too. 
#I think each of these subdirectories should have a CMakeLists.txt
add_subdirectory(Adder) 

#After compilation, link these libraries with the main executable
target_link_libraries(${PROJECT_NAME} adder) 

#This is not needed to run/compile/link/use the Adder library
#This specifies the directories of the libraries to be linked are 
#This Adder/ is in build/ directory. Its not the Adder in the current directory
target_link_directories(${PROJECT_NAME} PRIVATE Adder/)

#Specifies the include directories
#Can do #include<adder.h> instead of #include "Adder/adder.h"
target_include_directories(${PROJECT_NAME} PRIVATE Adder/)
