cmake_minimum_required(VERSION 3.5)
project(crypto)

include_directories("D:\\Develop\\Lib\\OpenSSL-Win64\\include")
# 搜索当前目录下的所有源文件
aux_source_directory(./ SRC)
file(GLOB HEADERS ${PROJECT_SOURCE_DIR}/*.h)

# 将当前目录下的源文件制作成静态库
add_library(crypto ${SRC} ${HEADERS})
target_link_libraries(crypto PRIVATE Qt${QT_VERSION_MAJOR}::Core
    "D:\\Develop\\Lib\\OpenSSL-Win64\\lib\\VC\\x64\\MD\\libcrypto.lib"
)
