# Quarto lab - shell
Nesse laboratório você deverá implementar sua própria shell. Você poderá chamá-la como quiser, mas ela deve ter uma interface de interação com o usuário.

# Avaliação
A avaliação do trabalho será feita em cima do código disponibilizado e do relatório das decisões tomadas ao longo do desenvolvimento. O relatório precisa incluir as principais decisões tomadas pela dupla no desenvolvimento da shell.

# Sobre a shell
A ideia principal do laboratório é vocês criarem uma shell básica, mas tem algumas funcionalidades que precisam estar presentes e que estão diretamente relacionadas com o que vocês vêm aprendendo ao longo da disciplina.

## Interação com o usuário
A shell deverá ter uma interface básica de interação com o usuário, como por exemplo:
```bash
mabshell> <comando>
```

## Comandos built-in
Sua shell deverá ser capaz de reconhecer alguns comandos *built-in* como `fg`, `bg`, `jobs` e `cd`.
Implemente outros comandos *built-in* que considerar relevantes.

Dica: você pode utilizar as funções de coordenação entre processos aprendidas em sala para mplementar essas funcionalidades.

## Outros comandos
Para executar outras funcionalidades que não sejam *built-in*, como por exemplo `ls`, você precisará passar o caminho inteiro para o binário.
No exemplo do `ls`, faríamos o seguinte:
```bash
mabshell> /usr/bin/ls -la
```

Também deverá ser possível executar binários próprios, por exemplo:
```bash
mabshell> ../03-buffer/buf1
```

## Controle de execução
Sua shell deverá ser capaz de colocar programas em *background* ao usar `&` no final da linha de comando. Utilizando o exemplo anterior, teríamos:
```bash
mabshell> ../03-buffer/buf1 &
```

Para colocar a execução desse programa em *foreground*, você deverá usar os comandos *built-in* especificados anteriormente aqui.
Esses comandos *built-in* devem funcionar como os que estamos familiarizados de uma shell Unix. Implementando suporte tanto a PID quanto a JID (usando %) como parâmetros.
Caso tenha alguma dúvida de como eles devem funcionar, você pode utilizar uma shell padrão para tirar dúvidas.

## Sinais
Será necessário implementar handlers para SIGINT (ctrl-c) e SIGSTP (ctrl-z). Ambos os sinais devem ser enviados para o processo que estiver em foreground naquele momento (e qualquer filho dele que existir). Se não tiver nenhum processo em foreground, não é necessário fazer nenhuma ação (como numa shell Unix usual).
Além disso, ao receber EOF (ctrl-d pela entrada padrão), pare a execução da shell.

## Simplificações
Não é necessário implementar pipe (`|`) nem redirecionamento de IO (`>`, `<`). A cada interação com a shell será passada apenas um comando por vez, não será necessário implementar múltiplos comandos por linha (permitindo uso de `;`), nem de execução sequencial/condicional com `&&` e `||`.

## Observações
**Não** pode utilizar a função `system()` para executar um comando de shell.
Por trás dos panos, `system(comando)` faz um `fork()` e executa `execl("/bin/sh", "sh", "-c", comando)`.
Então você estaria executando o comando em outra shell que não é a sua.

# Entrega do trabalho
Todos os arquivos de desenvolvimento do trabalho deverão ser entregues num zip ou tarball (não pode rar). Deverá ser incluído um Makefile para a compilação do projeto. Além disso, o arquivo de relatório (em pdf) também deverá ser entregue. Ele poderá ser incluído dentro do zip ou ser enviado diretamente pelo Classroom, como um arquivo extra.
Todos os arquivos deverão ser entregues pelo Classroom e só serão aceitos trabalhos enviados por lá.
