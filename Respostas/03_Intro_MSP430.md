## 1. Dada uma variável `a` do tipo `char` (um byte), escreva os trechos de código em C para:
### (a) Somente setar o bit menos significativo de `a`.
```C
  a |= 0x01; //Também pode-se usar o valor definido no header BIT0 = 0x01
```
### (b) Somente setar dois bits de `a`: o menos significativo e o segundo menos significativo.
```C
  a |= 0x03; //Também pode-se usar o valor definido no header, 
             //neste caso seria a soma dos valores (BIT0+BIT1)=0x03
  
```
  
### (c) Somente zerar o terceiro bit menos significativo de `a`.
  
### (d) Somente zerar o terceiro e o quarto bits menos significativo de `a`.
  
### (e) Somente inverter o bit mais significativo de `a`.
  
### (f) Inverter o nibble mais significativo de `a`, e setar o nibble menos significativo de `a`. 

2. Considerando a placa Launchpad do MSP430, escreva o código em C para piscar os dois LEDs ininterruptamente.

3. Considerando a placa Launchpad do MSP430, escreva o código em C para piscar duas vezes os dois LEDs sempre que o usuário pressionar o botão.

4. Considerando a placa Launchpad do MSP430, faça uma função em C que pisca os dois LEDs uma vez.

5. Reescreva o código da questão 2 usando a função da questão 4.

6. Reescreva o código da questão 3 usando a função da questão 4.
