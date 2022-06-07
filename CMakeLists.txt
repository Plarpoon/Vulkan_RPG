cmake_minimum_required(VERSION  3.5)
project(VulkanRPG LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 20)

add_subdirectory(external/engine)

add_executable(${PROJECT_NAME} src/main.cpp)

target_link_libraries(${PROJECT_NAME} VulkanRPG_engine)
target_include_directories(${PROJECT_NAME}
        PUBLIC
        PRIVATE
                    VulkanRPG_engine
)