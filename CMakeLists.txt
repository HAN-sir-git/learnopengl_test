cmake_minimum_required(VERSION 3.10)

project(main)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)

set(EXECUTABLE_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/output)   #设置编译好的exe文件输出目录

# 包含头文件目录
include_directories(include)

# 包含lib目录
link_directories(${CMAKE_SOURCE_DIR}/lib)

# 设置你想包含的目录前缀
set(SRC_PREFIX "02")
# 使用变量拼接路径
file(GLOB SOURCES "src/${SRC_PREFIX}*/*.cpp" "src/${SRC_PREFIX}*/*.h")

add_executable(main ${SOURCES})

# 链接lib目录下所有库（如glfw3.lib、glad.lib、opengl32.lib等）
target_link_libraries(main 
    glfw3
    glad
    opengl32
)