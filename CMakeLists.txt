cmake_minimum_required(VERSION 3.10)
project(MyGraphicsEngine)

set(CMAKE_CXX_STANDARD 17)

# Find Packages
find_package(OpenGL REQUIRED)
find_package(glfw3 REQUIRED)
find_package(GLEW REQUIRED)

# Include directories
include_directories(${GLEW_INCLUDE_DIRS} ${GLFW_INCLUDE_DIRS})

# Add executable
add_executable(MyEngine src/main.cpp)

# Link Libraries (Specific to macOS Frameworks)
target_link_libraries(MyEngine GLEW::GLEW glfw "-framework OpenGL" "-framework Cocoa" "-framework IOKit")
