# Segundo lab - bomb
Nesse laboratório, a ideia é analisar o binário [bomb](./bomb), compilado usando `gcc -m32 bomb.c -o bomb`.
O objetivo final desse laboratório é descobrir quais são as 4 strings necessárias para fazer a bomba não explodir.
Ao longo do caminho, documente todos os passos realizados e as descobertas feitas, destaque todos os passos necessários para encontrar e entender as senhas das bombas. Esse relatório será avaliado e essa avaliação será sua nota final do laboratório.

# Como fazer esse laboratório
Para descobrir as strings necessárias, utilize o GDB, carregando o binário:
```bash
gdb bomb
```
Utilize todo seu conhecimento sobre GDB e como um binário é organizado na memória para resolver o desafio. No Classroom tem uma lista de comandos úteis do GDB.

# Avaliação
A avaliação será feita em cima do relatório. Será levado em conta o entendimento que os alunos demonstrarem sobre o assunto, a qualidade para transmitir a informação de forma simples, e organização. Comente o máximo de linhas possível, qual o estado da pilha (quando achar relevante), e o valor dos registradores (também apenas quando achar relevante).

É recomendado que o relatório inclua screenshots para demonstrar o que estava sendo pensado.

# Instruções
As strings para defusar as bombas são passadas pelo `argv`, em ordem.
Ou seja, para rodar o programa, use:
```bash
./bomb <primeira-senha> <segunda-senha> <terceira-senha> <quarta-senha>
```

# Dúvidas
Esse laboratório é relativamente mais difícil do que o anterior. Algumas partes podem ser dificeis de entender de primeira.
Se você se sentir empacado em alguma parte, **não hesite em entrar em contato com o monitor pelo Telegram ou pelo Classroom**.