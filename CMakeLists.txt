#cmake -DCMAKE_CUDA_FLAGS="--gpu-architecture=sm_60" ..

cmake_minimum_required(VERSION 3.8 FATAL_ERROR)
project(ImGui LANGUAGES CXX)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

file(GLOB SOURCES ./*.cpp)
add_library(
    ImGui STATIC
    ${SOURCES}
)
message(${GLEW_INCLUDE_DIR})
target_link_libraries(ImGui)
target_include_directories(ImGui PUBLIC "${CMAKE_CURRENT_SOURCE_DIR}")

