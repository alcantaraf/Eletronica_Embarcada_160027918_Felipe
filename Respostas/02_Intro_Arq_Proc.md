## 1. Quais as diferenças entre os barramentos de dados e de endereços?

Barramento de dados serve para escrever ou ler dados na memória, já o de endereços serve para indicar o local de memória que será utilizado.

## 2. Quais são as diferenças entre as memórias RAM e ROM?

 A memória RAM é uma memória volátil, isso é quando a energia for cortada perde o que estiver guardado na mesma, a memória ROM consegue manter o conteudo ao se acabar a energia, pórem comparada com a RAM tem uma escrita mais lenta. 

## 3. Considere o código abaixo:
```C
#include <stdio.h>
int main(void)
{
	int i;
	printf("Insira um número inteiro: ");
	scanf("%d", &i);
	if(i%2)
		printf("%d eh impar.\n");
	else
		printf("%d eh par.\n");
	return 0;
}
```

Para este código, responda: 
### (a) A variável `i` é armazenada na memória RAM ou ROM? Por quê? 

 Na memória RAM, pois é uma variável que não tem necessidade de se guardada após a execução do programa e ainda com o programa em funcionamento é necessário um acesso rápido.

### (b) O programa compilado a partir deste código é armazenado na memória RAM ou ROM? Por quê?

 Memória ROM, pois ficará salvo no computador mesmo após o desligamento do mesmo.

## 4. Quais são as diferenças, vantagens e desvantagens das arquiteturas Harvard e Von Neumann?

A arquitetura Von Neumann, também conhecida como Princeton, é uma arquitetura mais simples, porém não permite acesso simultâneo nas memórias. Já a Harvard é uma arquitetura mais complexa e mais rápida, pois permite acesso simultâneo em ambas as memórias, porém existe a necessidade de instruções específicas. 

## 5. Considere a variável inteira `i`, armazenando o valor `0x8051ABCD`. Se `i` é armazenada na memória a partir do endereço `0x0200`, como ficam este byte e os seguintes, considerando que a memória é: (a) Little-endian; (b) Big-endian.

(a) CD-> 0X0200   //
    AB-> 0X0200 +1 //
    51-> 0X0200 +2 //
    80-> 0X0200 +3 //
(b) 80-> 0X0200 //
    51-> 0X0200 +1 //
    AB-> 0X0200 +2 //
    CD-> 0X0200 +3 //   
    
## 6. Sabendo que o processador do MSP430 tem registradores de 16 bits, como ele soma duas variáveis de 32 bits?


