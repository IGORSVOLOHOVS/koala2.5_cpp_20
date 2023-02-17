cmake_minimum_required(VERSION 3.11)

# project name
project(koala_project)

# set directory
set(KOALA_INCLUDE_DIRECTORY ${PROJECT_SOURCE_DIR}/include/koala)

# set headers
set(KOALA_INCLUDE 
${KOALA_INCLUDE_DIRECTORY}/koala_init.h 
${KOALA_INCLUDE_DIRECTORY}/koala_robot.h 
${KOALA_INCLUDE_DIRECTORY}/koala_serial.h 
${KOALA_INCLUDE_DIRECTORY}/koala_utils.h 
${KOALA_INCLUDE_DIRECTORY}/koala.h)

# koala.exe form main.cpp
add_executable(koala main.cpp ${KOALA_INCLUDE})

# set c++20 for koala
target_compile_features(koala PRIVATE cxx_std_20)

# link static lib
target_link_libraries(koala PUBLIC ${PROJECT_SOURCE_DIR}/lib/libkoala.a)