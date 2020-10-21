# Terceiro lab - buffer overflow
Nas últimas aulas, você aprendeu sobre uma vulnerabilidade conhecida como [Buffer Overflow](https://pt.wikipedia.org/wiki/Transbordamento_de_dados). Nesse laboratório, você irá tirar proveito de um programa com essa vulnerabilidade.

# Avaliação
Assim como no laboratório anterior, a entrega será em forma de relatório contendo todo o passo a passo feito para a exploração da vulnerabilidade nos desafios. Vale lembrar que esse relatório deverá ser entregue até a data limite no Classroom. Não será aceita nenhuma outra forma de envio.

# Como fazer esse laboratório
Esse lab consiste de três desafios.

## Antes de começar
Para facilitar seu trabalho na hora de explorar o binário, desative o ASLR no seu sistema rodando, como root:
```bash
echo 0 > /proc/sys/kernel/randomize_va_space
```
Essa configuração será desfeita quando você desligar o computador, então se for continuar o laboratório em outro dia, use esse comando novamente.

Detalhe: mesmo com ASLR, ainda pode ser fácil explorar essa vulnerabilidade num sistema de 32 bits.

![image](https://cdn.discordapp.com/attachments/696590063647326248/745098727404077104/unknown.png)

Fonte: https://www.blackhat.com/docs/asia-16/materials/asia-16-Marco-Gisbert-Exploiting-Linux-And-PaX-ASLRS-Weaknesses-On-32-And-64-Bit-Systems.pdf

## Primeiro desafio
Usando o binário [buf1](./buf1) você deverá se aproveitar do mau uso da função `gets()` para trocar a mensagem de boas vindas exibida na tela por "Tchau, mundo cruel".

### Responda:
1. Qual o tamanho do buffer que lê o nome do usuário?
2. Qual o tamanho do buffer de "Seja bem vindo!"?
3. Por que o primeiro print só para depois de "Tchau, mundo cruel"?

Inclua no relatório qualquer outra observação que considerar importante.

## Segundo desafio
Nesse desafio, encontrado em [buf2](./buf2), um pouco mais complexo, você deverá se aproveitar novamente do mau uso da função `gets()` para executar uma função que nunca é chamada no programa. Ou seja, apesar da função `codigo_morto` nunca ser chamada, você se aproveitará do buffer overflow para fazê-la ser executada.

### Responda:
1. Qual endereço do código morto?
2. Qual o tamanho do buffer de leitura?
3. Para onde aponta o ebp? E o `eip` de retorno da função que chama `main`?
4. Quantos bytes deve-se escrever até conseguir sobrescrever `eip`?
5. Qual valor deverá receber ser colocado para que eip aponte agora para `codigo_morto`?
6. Por que o programa não termina normalmente após ser explorado?

Dica importante: para conseguir inserir o endereço no binário, você deve inserí-lo em forma de *shellcode*. Pra isso, você pode usar um script em Python, do tipo:
```python
import struct
print(struct.pack("I", 0x08040000))
```

Rode esse programa conectando a saída padrão dele à entrada padrão do binário:
```bash
python exploit.py | ./buf2
```

Claro, um `exploit.py` só com o conteúdo acima não irá funcionar, pois você ainda precisará adicionar os bytes pra escrever o buffer inteiro e chegar até onde o `EIP` da função que chama a `main` está localizado.

## Terceiro desafio
Nesse último desafio, [buf3](./buf3), mais uma vez temos um programa utilizando `gets()` indevidamente, mas, diferentemente do desafio anterior, você não terá nenhuma função para executar. Dessa vez, você deverá inserir *shellcode* na pilha e fazer seu programa executá-lo. Assim, se bem sucedido, você deverá conseguir acesso a uma shell.

Novamente, destaque tudo que for importante durante a resolução do desafio no relatório.

O shellcode a ser inserido para executar uma shell pode ser encontrado [aqui](http://shell-storm.org/shellcode/).
