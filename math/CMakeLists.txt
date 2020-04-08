message(" Now is math/CL.txt")
# 查找当前目录下的所有源文件，并将名称保存到 DIR_LIB_SRCS 变量
aux_source_directory(. DIR_LIB_SRCS)

# 指定生成 MathFunctions 链接库
add_library (MathFunc SHARED ${DIR_LIB_SRCS})
#把这个库安装到系统usr目录中
install(TARGETS MathFunc  LIBRARY DESTINATION lib)
message( " Withdraw from math/CL.txt")

