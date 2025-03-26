project(VulkanSandbox)
cmake_minimum_required(VERSION 3.2)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED True)

find_package(Vulkan REQUIRED)

include_directories(${Vulkan_INCLUDE_DIRS})

SET(ENV_ROOT ${CMAKE_CURRENT_DIR})

SET(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_SOURCE_DIR}/bin)

ADD_SUBDIRECTORY(external)

add_executable(VulkanSandbox src/main.cc)

target_link_libraries(VulkanSandbox PRIVATE Vulkan::Vulkan glfw glm::glm)