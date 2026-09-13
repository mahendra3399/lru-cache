cmake_minimum_required(VERSION 3.16)

project(LRUCache
    VERSION 1.0
    LANGUAGES CXX
)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

add_library(lru_cache
    src/lru_cache.cpp
)

target_include_directories(lru_cache
    PUBLIC
        ${PROJECT_SOURCE_DIR}/include
)

add_executable(lru_tests
    tests/test_lru.cpp
)

target_link_libraries(lru_tests
    PRIVATE lru_cache
)

add_executable(lru_benchmark
    benchmarks/benchmark.cpp
)

target_link_libraries(lru_benchmark
    PRIVATE lru_cache
)