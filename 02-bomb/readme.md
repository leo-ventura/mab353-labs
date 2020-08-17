# Segundo lab - bomb
Nesse laboratório, a ideia é analisar o binário [bomb](./bomb), compilado usando `gcc -m32 bomb.c -o bomb`.
O objetivo final desse laboratório é descobrir quais são as 4 strings necessárias para fazer a bomba não explodir.
Ao longo do caminho, documente todos os passos realizados e as descobertas feitas. Esse relatório será sua nota final do laboratório.

# Como fazer esse laboratório
Para descobrir as strings necessárias, utilize o GDB, carregando o binário:
```bash
gdb bomb
```
Utilize todo seu conhecimento sobre GDB e como um binário é organizado na memória para resolver o desafio.

# Avaliação
A avaliação será feita em cima do relatório. Será levado em conta o entendimento que os alunos demonstrarem sobre o assunto, a qualidade para transmitir a informação de forma simples, e organização.

É recomendado que o relatório inclua screenshots para demonstrar o que estava sendo pensado.

# Instruções
As strings para defusar as bombas são passadas pelo `argv`, em ordem.
Ou seja, para rodar o programa, use:
```bash
./bomb <primeira-senha> <segunda-senha> <terceira-senha> <quarta-senha>
```