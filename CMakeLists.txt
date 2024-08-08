cmake_minimum_required(VERSION 3.1)
project(LearnOpenGL)
set(CMAKE_CXX_STANDARD 11)

#添加头文件
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/include)

#添加源文件
set(MAIN ${CMAKE_CURRENT_SOURCE_DIR}/src/25_spot_light/main.cpp)           # main.cpp 调试时记得改这行
# set(MAIN ${CMAKE_CURRENT_SOURCE_DIR}/src/23_direction_light/main.cpp)    # main.cpp 调试时记得改这行
file(GLOB IMGUI_SRC ${CMAKE_CURRENT_SOURCE_DIR}/include/imgui/*.cpp)

#设置动/静态库的路径
link_directories(${CMAKE_CURRENT_SOURCE_DIR}/lib)

# # 制作IMGUI库
# add_library(IMGUI SHARED ${IMGUI_SRC})
# set(LIBRARY_OUTPUT_PATH ${CMAKE_CURRENT_SOURCE_DIR}/lib)


#链接静态库
link_libraries(glfw3 opengl32 gdi32 GLAD)

#生成可执行程序
# set(EXECUTABLE_OUTPUT_PATH ${CMAKE_CURRENT_SOURCE_DIR}/output)  #可执行程序输出路径
add_executable(demo ${MAIN} ${IMGUI_SRC})


#链接动态库
#target_link_libraries(demo PUBLIC xxx)
# target_link_libraries(demo PUBLIC IMGUI)