

```shell
./koch test --failing --valgrind:off --megatest:off all
```

会调用Nim使用testament的各种测试套件

> [`testament`](https://nim-lang.org/docs/testament.html) 是Nim的单元测试标准库



### 参数解释

- --valgrind:off  截至 2024-12-24 valgrind 还不支持LoongArch64架构
- --megatest:off  [mega test](https://www.kiatoa.com/cgi-bin/fossils/megatest/index)


### 部分测试


#### 分类
see <nim-repo>/tests/readme.md

```shell
./koch test cat[egory] <cat> 

```

#### 单个

```shell
testament --nim:bin/nim run tests/<catergory>/<test>.nim
```



