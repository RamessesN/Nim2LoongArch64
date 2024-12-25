
将 compiler/tasm.nim 的两行

```asm
    mov %1, %0\n\t
    add $1, %0

```
|
v

`addi.w %0, %1, 1`
