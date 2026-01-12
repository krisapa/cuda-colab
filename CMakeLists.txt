cmake_minimum_required(VERSION 3.30)
project(cuda_colab CUDA)

set(CMAKE_CUDA_STANDARD 20)

set(CUDA_HEADERS_ROOT "/Users/krishpatel/cudasdk/cuda_headers" CACHE PATH "Local CUDA headers root for IDE indexing")

if (EXISTS "${CUDA_HEADERS_ROOT}/cuda_cudart/include/cuda_runtime.h")
  target_include_directories(cuda_colab PRIVATE
    "${CUDA_HEADERS_ROOT}/cuda_cudart/include"
    "${CUDA_HEADERS_ROOT}/cuda_cccl/include"
    "${CUDA_HEADERS_ROOT}/cuda_nvcc/include"
  )
endif()

add_executable(cuda_colab main.cu)

set_target_properties(cuda_colab PROPERTIES
        CUDA_SEPARABLE_COMPILATION ON)
