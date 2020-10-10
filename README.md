# mab353-labs
Desafios de laboratório para Computadores e Programação (MAB353) - UFRJ.

# Sobre
Nesse repositório se encontram os arquivos que servem como base para os laboratórios da disciplina MAB353. O objetivo de disponibilizá-los pelo GitHub é ter maior facilidade para os alunos conseguirem apenas clonar o repositório e terem todos os arquivos necessários. 

# Desafios
Para a avaliação final foram desenvolvidos 4 desafios, baseados nas diferentes partes da matéria que são cobertas ao longo do curso.

# Arquitetura
Para resolução dos laboratórios é obrigatório o uso de algum sistema operacional baseado em Linux, com suporte a execução de binários da arquitetura x86 (32-bits).

Nos slides presentes no Classroom é existem explicações de como habilitar suporte a x86 se você estiver usando um sistema x86_64 (64-bits).

# Compilação
Não se esqueça de sempre utilizar a flag `-m32` quando for compilar seu binário para testes. Um exemplo de compilação do primeiro desafio seria: `gcc -m32 -o bits bits.c`. O arquivo binário de saída estará nomeado como `bits`. Sem a opção `-o bits`, o arquivo de saída segue o nome padrão `a.out`.

# Como utilizar esse repositório
Para resolver os desafios, 3 passos são esperados do aluno:
1. Clonar esse repositório
2. Alterar o arquivo para o desafio
3. Enviar o arquivo pelo Classroom

**É mandatório o envio do arquivo pelo Classroom até a data limite.** Envios atrasados não serão corrigidos e receberão 0. O único lugar para envio dos arquivos será o Classroom. Envio por nenhuma outra plataforma será aceito.

# Clonando o repositório
Clonar o repositório copiará todos os arquivos presentes aqui para o seu computador. Fazê-lo é bem fácil:
```bash
git clone https://github.com/leo-ventura/mab353-labs.git
```

Isso irá criar um diretório chamado `mab353-labs` no diretório em que você executou o comando.
Nele você encontrará os arquivos necessários para fazer os laboratórios.

# Como fazer os desafios
Em cada diretório ([01-bits](./01-bits), [02-bomb](./02-bomb), [03-buffer](./03-buffer), [04-shell](./04-shell)) existe um readme específico explicando como cada desafio deverá ser resolvido.

# Contato
Qualquer dúvida em relação aos laboratórios poderá ser tirada no nosso grupo no Telegram ou conversando comigo no privado. Não hesite em mandar mensagem se estiver travado em algum dos desafios.