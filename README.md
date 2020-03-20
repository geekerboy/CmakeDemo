# CmakeDemo

The code references https://github.com/wzpan/cmake-demo

2020.1.12

The project contains message add_executable project PROJECT_BINARY_DIR PROJECT_SOURCE_DIR add_subdirectory add_library target_link_library 等语法的使用，借助meessage输出的信息，更加明白了   add_subdirectory的便利性以及编译的顺序，也尝试了out-of-source的编译方式

2020.1.12晚些时候
把生成的链接库以及头文件安装到/usr相应的位置上

2020.3.20
添加动态输入计算某个数的整数幂的值（第一个数是底数，第二个是指数）
实践发现，只安装库文件，不安装头文件也可以正常运行(新建build文件夹，编译后只保留可执行文件，其余文件直接删除）？？？？
