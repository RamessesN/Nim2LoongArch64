
需要超级用户(root)权限

```shell

# bin
for fn in nim nimble nimsuggest nimgrep; do cp ~loongson/build_nim/Nim/bin/$fn /usr/bin/$fn; done

# nim standard lib
mkdir /usr/lib/nim
cp -r ~loongson/build_nim/Nim/lib/ /usr/lib/nim/lib

# doc
mkdir /usr/lib/nim/doc
cp ~loongson/build_nim/Nim/doc/nimdoc.c* /usr/lib/nim/doc/

# tools
mkdir /usr/lib/nim/tools/
cp ~loongson/build_nim/Nim/tools/debug/nim-gdb.py /usr/lib/nim/tools/
mkdir /usr/lib/nim/tools/dochack/

# cfg
mkdir /etc/nim
cp ~loongson/build_nim/Nim/config/* /etc/nim/
```

