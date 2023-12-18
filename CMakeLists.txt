cmake_minimum_required(VERSION 3.25.1)

#set(CMAKE_TOOLCHAIN_FILE "~/vcpkg/scripts/buildsystems/vcpkg.cmake")

project(mysourcecpp)

add_executable(${PROJECT_NAME} main.cpp)

#set(CMAKE_PREFIX_PATH "~/vcpkg/scripts/buildsystems/vcpkg.cmake")

add_subdirectory(mylibs)

target_include_directories(${PROJECT_NAME} PUBLIC mylibs)

target_link_directories(${PROJECT_NAME} PRIVATE mylibs)

target_link_libraries(${PROJECT_NAME} mathsLab)

include_directories("${CMAKE_CURRENT_SOURCE_DIR}/mylibs") 

add_definitions(-DCMAKE_EXPORT_COMPILE_COMMANDS=ON)

