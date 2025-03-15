cmake_minimum_required(VERSION 3.10)
project(ImTest LANGUAGES C CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Find libImGui
find_package(SDL2 REQUIRED)
find_package(SDL2_ttf REQUIRED)
find_package(SDL2_image REQUIRED)
find_package(OpenGL REQUIRED)
find_package(libImGui REQUIRED)

# Add the example executable
add_executable(${PROJECT_NAME} main.cpp)

# Link libImGui
target_link_libraries(${PROJECT_NAME} PRIVATE libImGui)

# Include libImGui headers
target_include_directories(${PROJECT_NAME} PRIVATE ${libImGui_INCLUDE_DIRS})