cmake_minimum_required(VERSION 2.8.11)

project(eigencuda)

find_package(CUDA REQUIRED)
add_definitions(-DUSE_CUDA)

set(SOURCE_FILES
    src/test.cpp
    src/kernel.cu
    src/kernel.cpp
)

include_directories( test PUBLIC ${PROJECT_SOURCE_DIR}/include ${PROJECT_SOURCE_DIR}/thirdparty/eigen)
cuda_add_executable( test main.cpp ${SOURCE_FILES} )
