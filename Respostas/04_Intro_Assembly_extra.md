Para todas as questões, considere que as variáveis `f`, `g`, `h`, `i` e `j` são do tipo inteiro (16 bits na arquitetura do MSP430), e que o vetor `A[]` é do tipo inteiro. Estas variáveis estão armazenadas nos seguintes registradores:
- f: R4
- g: R5
- h: R6
- i: R7
- j: R8
- A: R9
Utilize os registradores R11, R12, R13, R14 e R15 para armazenar valores temporários.

#### 1. Traduza as seguintes linhas em C para a linguagem assembly do MSP430. Utilize somente as seguintes instruções: mov.w, add.w, sub.w, clr.w, dec.w, decd.w, inc.w e incd.w.

##### (a) `f *= 5;`
```Assembly
multiplica5x:
  add.w R4, R4 ;(f+f)
  add.w R4, R4 ;(f+f+f)
  add.w R4, R4 ;(f+f+f+f)
  add.w R4, R4 ;(f+f+f+f)
```
##### (b) `g *= 6;`
```Assembly
Multiplica6x:
  mov.w R5, R11
  add.w R5, R5 ;g+g
  add.w R11, R5; g+g+g
  add.w R5, R5; (g+g+g) + (g+g+g)
```
##### (c) `A[2] = 6*A[1] + 5*A[0];`
```Assembly
mov.w 2(R9), R15
mov.w 1(R9), R14
multiplica5x:
  add.w R14, R14 ;(f+f)
  add.w R14, R14 ;(f+f+f)
  add.w R14, R14 ;(f+f+f+f)
  add.w R14, R14 ;(f+f+f+f+f)
  mov.w R14, 4(R9)
Multiplica6x:
  mov.w R15, R11
  add.w R15, R15 ;g+g
  add.w R11, R15; g+g+g
  add.w R15, R15; (g+g+g) + (g+g+g)
add R15,4(R9)  
```
##### (d) `A[3] = 3*f - 5*h;`
```Assembly
mov.w R4, R15
multiplica3x:
  add.w R4, R4 ;(f+f)
  add.w R15, R4 ;(f+f+f)
mov.w R4, 8(R9)
multiplica5x:
  add.w R6, R6 ;(h+h)
  add.w R6, R6 ;(h+h+h)
  add.w R6, R6 ;(h+h+h+h)
  add.w R6, R6 ;(h+h+h+h+h)
sub.w R6,8(R9)

```
##### (e) `A[5] = 6*(f - 2*h);`
```Assembly
sub.w R6,R4
sub.w R6, R4
mov.w R4,R15
Multiplica6x:
  mov.w R15, R11
  add.w R15, R15 ;f+f
  add.w R11, R15; f+f+f
  add.w R15, R15; (f+f+f) + (f+f+f)
mov.w R15, 32(R9)  
```
