cmake_minimum_required(VERSION  3.5)
project(VulkanRPG_engine LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 20)

# import external libraries
add_subdirectory(external/glm)
add_subdirectory(external/glfw)

add_library(${PROJECT_NAME} src/engine.cpp)

target_include_directories(${PROJECT_NAME}
        PUBLIC
                    $<INSTALL_INTERFACE:include>
                    $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>
                    glm
        PRIVATE
)

target_link_directories(${PROJECT_NAME}
        PUBLIC
            glm
        PRIVATE
)