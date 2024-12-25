
# Build Nim from C source

## 为什么会有csources\_v2
Nim编译器 由 Nim语言实现，但是对于尚无法取得Nim编译器的平台(如尚未完成迁移的平台）,
这陷入了类似鸡生蛋的循环。

这时候，得益于Nim可以编译为C的特性，我们可以从相应的C代码编译得到第一个Nim,

该Nim一般不适于直接使用（一般版本较低）， 而是用于编译Nim编译器源代码

通过引入C这一被广泛支持的语言作为中间层，极大地扩展了Nim的普适性、减小了迁移难度。

Nim官方维护了大量平台的C source，版本号跟进Nim主版本号，为v2：

<https://github.com/nim-lang/csources_v2>



## 修改


使用现有的csources (commit: [86742fb02c66](https://github.com/nim-lang/csources_v2/commit/86742fb02c6606ab01a532a0085784effb2e753e))

编译则报错:

```plain
makefile:899: *** no C code generated for: [linux: loongarch64]。 
```


为了编译获得在该LoongArch PC上的第一个Nim编译器，


修改 csources\_v2/makefile。

以下是使用

```shell
git difftool -- makefile
```

的输出

![](../../../assets/csources_v2_makefile_diff.png)



之后执行`make`即可获得nim编译器。

之后使用该编译器编译Nim编译器源代码得到新版Nim编译器。


