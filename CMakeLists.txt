cmake_minimum_required(VERSION 3.16)
project(MeshShaderDemo)

set(CMAKE_CXX_STANDARD 17)
find_package(Vulkan REQUIRED)

add_subdirectory(third_party/glfw-3.3.8)
SET(GLM_TEST_ENABLE OFF CACHE BOOL "GLM Build unit tests")
add_subdirectory(third_party/glm-0.9.9.8/glm      EXCLUDE_FROM_ALL)

add_executable(${PROJECT_NAME} MeshShaderDemo.cpp)

target_link_libraries(${PROJECT_NAME} glfw ${GLFW_LIBRARIES} Vulkan::Vulkan glm::glm)