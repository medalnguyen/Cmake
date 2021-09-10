cmake_minimum_required(VERSION 3.21.1)

project(Learn)

add_executable(${PROJECT_NAME} main.cpp)

# Tạo đường dẫn đến thư mục con
add_subdirectory(include/Adder)

add_subdirectory(include/GLFW)

# Tạo ra thư viên trong folder build
target_include_directories(${PROJECT_NAME} 
    PUBLIC include/Adder 
    PUBLIC include/GLFW/include 
)

# Liên kết với file source vời folder include
target_link_directories(${PROJECT_NAME} 
    PRIVATE include/Adder
    PRIVATE include/GLFW/src
)

target_link_libraries(${PROJECT_NAME} adder glfw)