# Primeiro lab - bits
No início da matéria, vemos como as operações bitwise funcionam mais internamente. Nesse primeiro desafio, buscamos implementar algumas ações comuns por meio de outros operadores (com foco em operadores bitwise).

# Como fazer esse laboratório
O `return -1` de cada função deverá ser substituído pelo menor número de operações possíveis para realizar aquele objetivo usando o subconjunto de operadores especificados no comentário acima de cada função.

Pelo comentário também é possível ver quantas operações eu utilizei para resolver aquele objetivo. Isso deve ajudar aqueles que não conseguirem pensar em uma solução imediata.

# Avaliação
É importante ressaltar também que se não conseguirem resolver com o número máximo de operações especificadas, a avaliação daquela função será zerada.

Além disso, cada função também será avaliada baseada na **explicação dos passos**. Não adianta copiar código sem entender o que aconteceu e esperar que vá receber o ponto inteiro. Pelo contrário, **se não houver explicação do que foi feito ela será zerada**.

Ah, detalhe: **quem conseguir resolver com menos operações do que o monitor, ganhará bônus**.

# Instruções
Para testar basta compilar e rodar.

É possível fazer a compilação pela linha de comando com `gcc -m32 bits.c -o bits` ou usando o [Makefile](./Makefile).
Por fim, rode como qualquer executável: `./bits`

# FAQ
1. O que conta como uma operação?

Apenas o que realizar alguma conta ou modificação dos valores. Consequentemente, parênteses não contam como operações.

Exemplo: `x + ((~x) & (x & 0x1))` tem 4 operações: +, ~, 2 vezes &.

2. Pode atribuição?

Sim, desde que seja atribuição a int32_t. Qualquer outra atribuição está proibida. Ou seja:
```c
int32_t flipped = ~x;   // válido
uint32_t flipped = ~x;  // inválido
```

3. Pode if-else, for, while, etc?

Não. Apenas operadores e atribuições são permitidas. Vale ressaltar também que não são obrigatórias atribuições, os resultados podem ser feitos em uma linha.
