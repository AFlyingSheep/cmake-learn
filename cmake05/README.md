# cmake 05

- 构建了静态库(static)与动态库(shared)，同时给出了一个同事生成静态、动态库的方法

- 安装库方法:

```cpp

    // 本例中我们将 hello 的共享库安装到<prefix>/lib目录
    // 将 hello.h 安装到<prefix>/include/hello 目录
    // 

```

1. 安装头文件:

```cpp

    INSTALL(FILES hello.h DESTINATION include/hello)

```
2. 安装二进制文件(.so, .a)
```cpp

    // 二进制，静态库，动态库安装都用TARGETS
    // ARCHIVE 特指静态库，LIBRARY 特指动态库，RUNTIME 特指可执行目标二进制。
    // INSTALL中的hello, hello_static分别是ADD_LIBRARY中的名称
    INSTALL(TARGETS hello hello_static LIBRARY DESTINATION lib ARCHIVE DESTINATION lib)

```
注意：安装的时候，指定一下路径，放到系统下

`cmake -D CMAKE_INSTALL_PREFIX=/usr ..`
