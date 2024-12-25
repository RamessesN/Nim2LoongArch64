## <center>Nim 展示文档<center>

#### （一）Nim 模块编译测试

*在 build_nim/Nim 下进行编译测试*

```bash
./koch test
```



#### （二）Nim 基本命令信息

- 查看帮助文档

```powershell
nim --help
```

- 查看 Nim 编译器版本信息

```powershell
nim --version
```



#### （三）Nim 交互式执行命令

- 直接执行表达式或命令

```powershell
nim --hints:off --eval:"echo 5 * 4"	
```

- Nim 交互式运行环境 (REPL)，

```powershell
nim --hints:off secret	
```

*以下为简单测试示例*

```powershell
>>> echo type(1.0)

>>> high(int)

>>> from std/math import sqrt
>>> sqrt 9.1
```



#### （四）Nim 基本命令行操作

*编写 testArgs.nim 文件内容如下*

```nim
##[
	一个简单的*IO*示例
- 读取一行命令行输入
- 输出`*result: *` + 输入
]##

template main* =
    ## doc for `main`
    let name = readLine(stdin)
    echo "result: ", name
    
main
```

进行相关编译执行测试

- 编译并执行 .nim 文件

```powershell
nim r --hints:off testArgs.nim
nim 					//执行输入
```

- 编译生成可执行文件

```powershell
nim c --hints:off testArgs.nim	
./testArgs
Nim						//执行输入
```

- 根据源代码生成文档

```powershell
nim doc --hints:off testArgs.nim
```

在生成 htmldocs 文件夹下利用 Python3 环境启动 HTTP 服务器进行内容查看

```powershell
ip addr					//查看 loongson 服务器 IP 地址
python3 -m http.server
```

浏览器访问 IP 地址 (192.168.2.198) 查看 testArgs.html 生成文档

