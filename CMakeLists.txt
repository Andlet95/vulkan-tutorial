cmake_minimum_required(VERSION 4.0)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_FLAGS "-Wall -O2")

project(vulkan-tutorial)

add_executable(${PROJECT_NAME})

target_sources(${PROJECT_NAME} PRIVATE main.cpp)

find_package(glfw3 REQUIRED)
find_package(Vulkan REQUIRED)
find_package(glm REQUIRED)
find_package(tinyobjloader REQUIRED)

add_subdirectory(shaders)
add_subdirectory(textures)
add_subdirectory(models)

target_link_libraries(${PROJECT_NAME}
    Vulkan::Vulkan
    glfw
    glm::glm
)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)
