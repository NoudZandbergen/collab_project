cmake_minimum_required(VERSION 3.0.0)
project(collab_project VERSION 0.1.0)

# Enable testing
include(CTest)
enable_testing()

# Create a runnable executable
add_executable(collab_project src/main.cpp)

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR})
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR})

# Add the collab_engine
add_subdirectory(collab_engine)
target_link_libraries(collab_project LINK_PUBLIC collab_engine)

# Enable packing
set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)
