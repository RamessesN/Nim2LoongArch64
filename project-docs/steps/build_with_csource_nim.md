


### 编译旧版本的C代码

编译得到 `bin/nim_csources_<git-commit>`


### 使用由旧版C代码编译得到的nim编译现在的nim源码

#### 编译构建工具
```shell
nim c koch
```

> [`koch`](https://nim-lang.org/docs/koch.html) 是构建Nim的工具，用于在各种系统下开发和编译Nim编译器本身


### 编译Nim

```shell
./koch boot -d:release --cpu:loongarch64
```



> 需要追加 --cpu:loongarch64 参数，否则使用的还是原来Nim的hostCPU信息




