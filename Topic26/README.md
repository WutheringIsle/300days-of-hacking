# Learning Assembly Lannguage (INTEL SYNTAX)


## X86 

This is a 32 bit register architechture. 

### Registers
- For Floating point values
    - XMM0 to XMM15 
- General Purpose: EAX, EBX, ECX, EDX,  ESI, EDI, EBP and ESP 
    - EAX : Accumulator registers (for arithmetic)
    - EBX : Base registers (for base pointer, sometimes return value and arguments to syscall)
    - ECX : Counter Register
    - EDX : Data registers


### BITS AND BYTES

Bit is one binary.
Nibble is 4 bits, one digit of a hex.
Byte is 8 bits, two digit hex.
Word is 2 bytes.
Double Word (DWORD) is 4 bytes. Twice the size of a word.
Quad Word (QWORD) is 8 bytes. Four times the size of a word. 



### Common Terms to know before proceeding (with Simple Assembly example)

- An immediate value (or just immediate, sometimes IM) is something like the number 12. An immediate value is not a memory address or register, instead, it's some sort of constant data.

- A register is referring to something like RAX, RBX, R12, AL, etc.

- Memory or a memory address refers to a location in memory (a memory address) such as 0x7FFF842B.


### Operand


#### Mul
takes only one one operand and multiplies it with the value stored in EAX and stores the result in EDX:EAX.

```x86asm
mov EAX, 25
mov EBX, 5
mul EBX ; Multiplies EAX (25) with EBX (5)
```

### Div

takes only one one operand and dividesEAX with the value stored in the operanf and stores the result in EDX:EAX.

```x86asm
mov EAX, 18
mov EBX, 3
div EBX ; Divides EAX (18) by EBX (3)
```

### CMP

CMP compares two operands and sets the appropriate flags depending on the result.

```x86asm
mov RAX, 8
cmp RAX, 5
```


### NOP

Nop is short for No Operation. This instruction effectively does nothing. its usually used for padding.



### Example

```x86asm
mov RAX, x          ; move variable from memory into register
cmp RAX, 4          ; compare immediate value with register value, set flag based on comparation
jne 0x7FFF842B      ; (ret) jump to a memory address 
call func1
ret
```



### STACK

![Alt text](image.png)




### Arrays
Arrays store multiple pieces of data which are the same type sequentially in memory. Let's say you have an array of 5 integers that starts at the address of 0x4000. 
The size of the array is 20 bytes since each integer is 4 bytes. The first integer is at 0x4000+0x0, the second is at 0x4000+0x04, and so on.

Let's say we have an array of 4 integers that starts at the address of 0x4000. 

```c
int numbers[4] = {0, 1, 2, 3};
```

In memory
```x86asm
0x4000: 0 ; 4 bytes long
0x4004: 1 
0x4008: 2
0x4012: 3
```

### Classes


```x86asm
mov RAX, 0x4000     ; RAX = Address of the class and the age variable (offset 0)
lea RBX, [RAX+0x4]  ; RBX = Address of height
lea RCX, [RAX+0x8]  ; RCX = Address of name
mov [RAX], 0x32     ; age = 50
mov [RBX], 0x48     ; height = 72
mov [RCX], 0x424F42 ; name = "BOB"
```

## X86_64

Floating point : YMM0 to YMM15,  256-bit wide each and can hold 4 64-bit values or 8 32-bit values


## ARM











https://tryhackme.com/room/win64assembly