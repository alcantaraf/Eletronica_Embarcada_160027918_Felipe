### 1. (a) Escreva uma função em C que calcule a raiz quadrada `x` de uma variável `S` do tipo float, utilizando o seguinte algoritmo: após `n+1` iterações, a raiz quadrada de `S` é dada por

```C
x(n+1) = (x(n) + S/x(n))/2
```

O protótipo da função é:

```C
unsigned int Raiz_Quadrada(unsigned int S);
```
##### Resposta:
```C
unsigned int Raiz_quadrada(unsigned int S)
{
  int i;
  float x = 1;
  if S < 2
    return S;
  else
  {
    for(i = 0; i < 25; i++)
      x = (x + S/x)/2;
      return x;
  }
}
```
#### (b) Escreva a sub-rotina equivalente na linguagem Assembly do MSP430. A variável `S` é fornecida pelo registrador R15, e a raiz quadrada de `S` (ou seja, a variável `x`) é fornecida pelo registrador R15 também.

##### Resposta:
```Assembly
Raiz_quadrada: cmp #2,R15
               jge Raiz_menor_2
               push R4
               push R5
               push R6
               clr R5
               mov R15, R4
               mov #1, R5
Raiz_loop: cmp #25, R5
           jz End_Raiz
           mov R4, R15
           mov R5, R14
           call #div
           add R5, R15
           mov R15, R6
           rra R6
           inc R5
           jmp Raiz_loop
Raiz_end: mov R6, R15
          pop R6
          pop R5
          pop R4
Raiz_menor_2: ret


```

### 2. (a) Escreva uma função em C que calcule `x` elevado à `N`-ésima potência, seguindo o seguinte protótipo: 

```C
int Potencia(int x, int N);
```
##### Resposta:

#### (b) Escreva a sub-rotina equivalente na linguagem Assembly do MSP430. `x` e `n` são fornecidos através dos registradores R15 e R14, respectivamente, e a saída deverá ser fornecida no registrador R15.
