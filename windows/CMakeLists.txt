cmake_minimum_required(VERSION 3.5)
project(windows)

# 搜索当前目录下的所有源文件
aux_source_directory(./ SRC)

# # 搜索头文件和UI 文件
file(GLOB HEADERS ${PROJECT_SOURCE_DIR}/*.h)
file(GLOB UIS ${CMAKE_CURRENT_SOURCE_DIR}/*.ui)

# 将当前目录下的源文件制作成静态库
add_library(windows ${SRC} ${HEADERS} ${UIS}
)
target_link_libraries(windows PRIVATE Qt${QT_VERSION_MAJOR}::Core
    Qt${QT_VERSION_MAJOR}::Widgets
    Qt${QT_VERSION_MAJOR}::Multimedia
)
