cmake_minimum_required(VERSION 3.30)
project(cuda_colab CUDA)

set(CMAKE_CUDA_STANDARD 20)

add_executable(cuda_colab main.cu)

set_target_properties(cuda_colab PROPERTIES
        CUDA_SEPARABLE_COMPILATION ON)
