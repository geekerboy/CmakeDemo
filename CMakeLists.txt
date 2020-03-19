# CMake 最低版本号要求
cmake_minimum_required (VERSION 2.8)

# 项目信息
project (cmake_demo)
#同时定义 PROJECT_BINARY_DIR  PROJECT_SOURCE_DIR 两个隐式变量
message(${PROJECT_BINARY_DIR} " is the binary dir")
message(${PROJECT_SOURCE_DIR} " is the source dir")
message(${EXECUTABLE_OUTPUT_PATH} " is the origin executable output dir")
message(${LIBRARY_OUTPUT_PATH} " is the origin library output dir")
message(${CMAKE_INSTALL_PREFIX} " is the origin installed dir")
set(CMAKE_INSTALL_PREFIX /usr)
message("now " ${CMAKE_INSTALL_PREFIX} " is the installed dir")

# 查找目录下的所有源文件，并将名称保存到 DIR_SRCS 变量
#aux_source_directory(. DIR_SRCS)
#message(status "DIR_SRCS is ${DIR_SRCS}")
#add_executable(Demo ${DIR_SRCS})

set(FILE "main.cc") #可不加引号，文件名有空格必须加
message(status " FILE is ${FILE}")
add_executable(Demo ${FILE})

message(status " Before cd math")
#set(EXECUTABLE_OUTPUT_PATH ${PROJECT_BINARY_DIR}/bin)
# 添加存放源文件的子目录
add_subdirectory(math)
message(status " Back into main dir")
#安装.h文件到．．．目录,第一次编译的时候include前面加了个/,结果直接安装到/include文件下,不是想要的/usr/include
install(FILES math/MathFunctions.h DESTINATION include/mathfunc)
# 添加链接库
target_link_libraries(Demo MathFunc)
