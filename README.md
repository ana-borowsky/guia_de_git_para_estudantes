# Guia de git para estudantes
Este é um guia básico e descontraído de git feito por uma estudante para outros estudantes! 

:star:Se este guia lhe foi útil, ou você aprendeu a usar o git comigo, deixa sua estrelinha como agradecimento!:star:

Achou que faltou algo neste guia? Crie um novo [issue](https://github.com/ana-borowsky/guia_de_git_para_estudantes/issues/new) que eu responderei o quanto antes!

## Índice
- 1. [Como usar o git?](#1-como-usar-o-git)
  - 1.1 [Afinal, para que serve o git?](#11-afinal-para-que-serve-o-git)
  - 1.2 [Como salvar o código no git? Também conhecido como commit](#12-como-salvar-o-código-no-git-também-conhecido-como-commit)
  - 1.3 [Regras básicas de sobrevivência do commit](#13-regras-básicas-de-sobrevivência-do-commit)
    - 1.3.1 [A primeira e mais importante dica](#131-a-primeira-e-mais-importante-dica)
    - 1.3.2 [O que deve ter em um commit?](#132-o-que-deve-ter-em-um-commit)
    - 1.3.3 [Padrões de mensagem de commit](#133-padrões-de-mensagem-de-commit)
  - 1.4 [Resumo padrões commit](#14-resumo-padrões-commit)
  - 1.5 [Resumo comandos commit](#15-resumo-comandos-commit)
- 2. [Uso de branches](#2-uso-de-branches)
  - 2.1 [O que são branches?](#21-o-que-são-branches)
  - 2.2 [Como criar branches?](#22-como-criar-branches)
  - 2.3 [Como trocar de branches?](#23-como-trocar-de-branches)
  - 2.4 [Como saber em qual branch estou?](#24-como-saber-em-qual-branch-estou)
  - 2.5 [Como ver os branches no GitHub?](#25-como-ver-os-branches-no-github)
  - 2.6 [Procedimento merge/pull request](#26-procedimento-merge-pull-request)
  - 2.7 [Comecei a alterar o código mas esqueci de criar um branch!](#27-comecei-a-alterar-o-código-mas-esqueci-de-criar-um-branch)
  - 2.8 [Fiz push na Main!!](#28-fiz-push-na-main)
  - 2.9 [Procedimento rebase](#29-procedimento-rebase)
  - 2.10 [Você pode entrar no branch dos amiguinhos](#210-você-pode-entrar-no-branch-dos-amiguinhos)
  - 2.11 [Resumo comandos branch](#211-resumo-comandos-branch)
    
## 1. Como usar o git?
É importante mencionar que não abordarei neste guia a parte de instalação/ setup do git, e sim, o seu uso!

Ah, nós também faremos uso do git via linha de comando e não via aplicativo desktop.
### 1.1 Afinal, para que serve o git?
O git é um sistema de versionamento de código. Mas o que significa isso? Bem, sabe quando você está fazendo um trabalho e começa a salvar como versão1, versão2, versãofinal, versãofinalfinalagoravai, etc? Então, é isso que o git faz, só que direito.

Com isso, você consegue:
 - ter um controle muito bom de qualquer trabalho,
 - acompanhar a evolução,
 - ter a certeza de que pode voltar para uma parte do código que funciona caso você resolva fazer uma mudança que dê ruim (sem depender do crtl + z)
 - acesso ao código de vários computadores de forma facilitada
 - controle melhor de trabalhos em grupo

Eu prometo que depois que você aprender a usar o git, você não vai conseguir entender como as pessoas viviam antes dele.

### 1.2 Como salvar o código no git? Também conhecido como commit
Primeiramente, o que é o commit? É mais ou menos o equivalente a salvar o seu código no git (não no seu computador). 
Existem algumas regras para fazer isso da maneira a aproveitar melhor essa feature, as quais serão explicadas ao longo deste capítulo, mas vamos começar pelo comando de como fazer isso.

Se seu código está pronto para o commit, dê o comando:
>git status

Isso vai te mostrar se tem arquivos que foram modificados para serem commitados. Se você modificou o arquivo, ele deve aparecer em vermelho no console.

Agora você vai adicionar o que quer commitar. Para adicionar todos os arquivos do projeto que foram modificados:
>git add .

Para adicionar somente um arquivo:
>git add nome_do_arquivo.py

Agora faça novamente o comando _git status_ e veja se os arquivos que você quer commitar ficaram verdinhos. Caso isso não tenha acontecido, provavelmente você não está na pasta certa na linha de comando. É preciso que os arquivos fiquem verdes para que sejam commitados.

Agora vamos fazer o commit efetivamente dito.
  >git commit -m “Escreva aqui a mensagem do commit”

Você já commitou, mas se você abrir o github no repositório do projeto, verá que sua mudança ainda não está aparecendo. Para que ela apareça, é preciso fazer o _push_:
  >git push

Agora sim, abra o github no repositório do projeto e verá que o seu código agora está aparecendo lá.

![Image](https://github.com/user-attachments/assets/4827202e-153f-4ff5-af72-45cec62e67ab)

## 1.3 Regras básicas de sobrevivência do commit
Para fazer o melhor aproveitamento do commit, existe uma série de dicas que facilitarão muito a sua vida, as quais serão brevemente explicadas abaixo.

#### 1.3.1 A primeira e mais importante dica

**Só faça commit de códigos que funcionem**. 

Assim, você consegue voltar para o último commit caso faça alguma alteração que faça com que o código pare de funcionar.

#### 1.3.2 O que deve ter em um commit?
Para que um commit seja super legível, o ideal é que você faça somente **uma coisa em cada um**.

Evite fazer um commit que implemente uma função em um arquivo, modifique a formatação do código em outro, e remova comentários em um terceiro. Pois dessa forma, quando você for ver o commit pelo github, terão mil alterações em mil arquivos diferentes, e ficará mais difícil achar a alteração importante que realmente foi o ponto alto do commit.

Então se quiser fazer essas três coisas mencionadas no exemplo, faça:
 - Um commit para implementar a função
 - Um para corrigir a formatação
 - Um para remover comentários

#### 1.3.3 Padrões de mensagem de commit
Sempre começar a mensagem com a primeira letra em maiúsculo, no tempo verbal imperativo afirmativo, ou seja, é como se fosse uma resposta à pergunta: o que este commit faz? 
As mensagens não devem ter ponto final.

**Exemplos:**

![Image](https://github.com/user-attachments/assets/862be7da-a4a8-4ffd-bbd1-9ea0b498e121)

A língua utilizada para os commits depende do projeto. Sempre combine com seus colegas qual será a utilizada para não ficar misturado.

Evitar commits genéricos e imprecisos como: 
- Faz pequenas alterações (quais?),
- Arruma bugs (que bugs?)
- Mexe na função imprimir (tá, mas o que foi mudado?)

A boa prática é sempre fazer commits façam só a mensagem do commit diz.

**Anti-exemplos**
Abaixo são mostrados alguns exemplos de como **não fazer commits** e os problemas com eles:

![Image](https://github.com/user-attachments/assets/430ddd48-1171-44a1-aff2-3b6621098a76)

O primeiro está errado pois: 
- Tempo verbal incorreto,
- Foram feitas três tarefas ao invés de uma,
- A própria descrição não é clara o suficiente. Eu só entendo porque não faz muito tempo que este trabalho foi feito e eu ainda lembro do que se trata.

O segundo errado:
 - Deveria ser chamado de "Inicia modelagem lógica do banco de dados", ao invés de utilizar o tempo verbal errado e ter "incompleto" no nome.

O terceiro errado:
 - Está em inglês, sendo que o padrão do trabalho foi decidido como sendo português,
 - Mensagem ruim. Eu só entendo o que quer dizer porque faz pouco tempo que o trabalho foi feito. 
 - Primeira letra não está em maiúsculo,
 - Tempo verbal incorreto.

### 1.4 Resumo padrões commit
  -  Só commite códigos que funcionem
  -  Só mexa em _uma coisa_ específica em cada commit
  -  Dê nomes que digam exatamente o que você fez naquele commit
    -  Resposta à pergunta: o que este commit faz?
    -  Sempre na mesma língua (ou tudo em português ou tudo em inglês)
    -  Primeira letra em maiúsculo
    -  Sem pontuação no final

### 1.5 Resumo comandos commit
> git add .

> git commit -m "Cria função remover"

> git push
  
## 2. Uso de branches
Se você reparou que para trabalhos em grupo, estava sendo um pouco complicado usar o git, pois você e seus colegas tinham que avisar quando estavam mexendo no projeto, e volta e meia alguém não avisava e acabava gerando confusão, seus problemas acabaram!

### 2.1 O que são branches?
Branches são derivações do código utilizados, normalmente, para adicionar novas funções ao programa. Ao utilizar branches, vários programadores podem trabalhar em um mesmo código ao mesmo tempo, ficando mais simples de resolver conflitos (diferenças entre os códigos). 

Mesmo quando se está trabalhando sozinho num código, esta é uma prática que é recomendada. Por exemplo: 

Imagine que você está construindo uma aplicação web e começa a implementação de uma nova função, mas acaba descobrindo que ela é mais complicada do que o esperado. O que você faz? Fica preso nela? Comenta parte do código?

Na realidade o mais fácil é você trabalhar nessa nova função em um novo branch. Assim, você pode apenas deixar esse branch interminado e abre outro para continuar o projeto até você ter a capacidade de voltar para esta parte.

Assim você continua com a main sempre funcionando sem precisar comentar parte do código para poder rodar.

Vamos mostrar agora com imagens, para ficar mais claro!
Na imagem 1, os alunos Ana, Giovanni e Gustavo tem uma versão da Main (código base) nos seus respectivos computadores e cada um ficou responsável por adicionar uma nova função ao programa. 

Cada um clonou o repositório do projeto localmente, e estão inicialmente no branch main. 

Para que cada um comece a lidar com a sua parte do projeto, a primeira coisa que devem fazer é criar branches. 

![Image](https://github.com/user-attachments/assets/23deaf28-bcf0-4ec9-a966-42548fbec4ad)

### 2.2 Como criar branches?
Na linha de comando, digite: 

  >git checkout -b nome-da-branch

Este comando troca de branch já criando um branch novo. Observe que o padrão para nomes de branches é ser tudo em minúsculo e com traços no lugar de espaços.

### 2.3 Como trocar de branches?

  >git checkout nome-da-branch

### 2.4 Como saber em qual branch estou?

  >git status

### 2.5 Como ver os branches no github?
Entre no repositório, e embaixo do nome do repositório irá mostrar o nome do branch. Na página inicial geralmente é o branch main que aparece. Clique nele e em seguida em view all branches.

![Image](https://github.com/user-attachments/assets/1ca4246b-ee7d-41c0-8a5f-c55c40ecd152)

Para deletar um branch, é só fazer este procedimento e clicar na lixeira. Depois de fazer o merge, ou caso desista de trabalhar neste branch, ele deve ser deletado.

### 2.6 Procedimento merge/ pull request
Você termina a parte do código em que estava trabalhando, realiza os testes, _verifica que tudo funciona direitinho_. Então é hora de juntar a sua parte com a base do projeto (main). 
- Primeiro: execute todos os passos do [Como salvar o código no git? Também conhecido como commit](#12-como-salvar-o-codigo-no-git-também-conhecido-como-commit).
- Apenas na primeira vez que fizer o push, você tem que dar o seguinte comando:
>git push --set-upstream origin nome-da-branch
- Avise a todos os colegas de equipe que irá abrir um PR (pull request)
- Abra o github no repositório do projeto e você verá uma mensagem em uma cor chamativa e com um botão ao lado escrito “compare & pull request”. Clique nele.

<img width="740" alt="Image" src="https://github.com/user-attachments/assets/f0a30448-dd96-4fc3-a7cd-54c47c97ed36" />


Ou entre no branch e faça por lá.


<img width="741" alt="Image" src="https://github.com/user-attachments/assets/9b5cbe7c-86b1-4313-b038-40b0a063d304" />

  Preencha todos os campos do pull request de maneira clara.
- Dê um assign para que outro membro da equipe verifique se o seu pull request está ok para ser mergeado (você também pode auto-aprovar seu PR se quiser)
- Após a aprovação do PR por você ou por um colega, siga com os passos que serão descritos logo mais.

Primeiro é interessante você saber que ao mergear um PR, o seu branch main local _não será automaticamente atualizado_. 

Após o PR mergeado:

Volte para o branch main:
  
>git checkout main

Confira se está na main com:

>git status

Atualize a sua main local com:

>git pull

- Delete o branch no github

<img width="731" alt="Image" src="https://github.com/user-attachments/assets/73619bf8-5a21-4397-8ed0-f7641762ff9e" />

- Avisar a todos da equipe que mergeou um novo PR, para que todos façam pull na main.
### 2.7 Comecei a alterar o código mas esqueci de criar um branch!

>git checkout -b nome-da-branch

Este comando irá levar suas alterações para esta nova branch.
### 2.8 Fiz push na Main!!
Quando se faz isso, você pula o verificador de merge do github, que verifica antes de fazer o merge se não há conflitos com a main. Isso poderá causar diversos problemas e seus colegas de trabalho _não ficarão nenhum pouco felizes._ Por isso é sempre importante: **antes de começar a codar, dê o comando git status para saber onde está e crie sua branch.** É possível bloquear o push direto na main pelas configurações do repositório no github, e isso é uma prática recomendada.
### 2.9 Procedimento rebase
Rebase faz exatamente o que o nome diz: troca a base. Quando uma pessoa faz um merge na main, essa main não é automaticamente atualizada. Pelo contrário, todo mundo continua com a branch antiga (antes do merge) em seus computadores. Isso nem sempre é um problema.  No exemplo abaixo (imagem 2), todos os programadores estão trabalhando em uma parte do código independente uma da outra. Logo, não há necessidade de atualizarem as suas bases, é só cada um fazer um merge que dará tudo certo.

![Image](https://github.com/user-attachments/assets/ea0a1db9-c0ee-4d5c-b47a-6c52ce2495f5)

É sempre bom saber que quando um membro da equipe faz um merge, a main é atualizada no github, mas não é automaticamente atualizada nos computadores de cada membro da equipe, como é mostrado na imagem 3.

![Image](https://github.com/user-attachments/assets/83d6340f-bdd6-4f93-b8b3-3632bb0fc4b7)

Vamos dizer que no exemplo da imagem 3, Giovanni não precisa saber como a Ana fez a função “remover” para terminar a sua parte do código. Então não há problemas em ele não atualizar sua main dentro de sua branch (embora no seu computador, ele deva fazer isso, como descrito no [Procedimento merge/pull request](#26-procedimento-merge-e-pull-request)). 

Já Gustavo prefere saber como Ana fez, já que a função na qual está trabalhando - inserir - é um pouco parecida, então ele opta por fazer o rebase e continuar o trabalho a partir disso. Em sua branch ele dá o seguinte comando:

>git rebase main

Esse comando irá trocar a main da branch pela atualizada. Após esse comando, podem aparecer muitos conflitos com o seu código. Caso nenhum problema aconteça, dê o comando:

>git rebase --continue

Caso aconteçam conflitos, resolva-os primeiro, e depois dê o comando mencionado anteriormente. Ou, caso queira desistir do rebase, dê o comando:

>git rebase --abort

Quando for fazer o push, será necessário fazer:

>git push --f

O git rebase reescreve o histórico de commits (muda o hash dos commits). Então, depois de um rebase, a sua branch local fica diferente da que está no repositório remoto. Por isso é necessário usar o push force. 

Em uma empresa, você vai demorar para ter permissão pra usar esse comando, mas em trabalhos da faculdade dá para usar. 

**Não é necessário fazer commit após fazer o rebase.**

E assim ficou a visão de Gustavo da main após o rebase:

![Image](https://github.com/user-attachments/assets/72f80711-fbdf-4e6b-8ae3-ad058e836686)

### 2.10 Você pode entrar no branch dos amiguinhos
Se seu colega já tiver feito push no branch dele, basta você fazer os seguintes comandos caso queira entrar neste branch:
>git checkout main
>git pull
>git checkout nome-do-branch-do-coleguinha

### 2.11 Resumo comandos branch
>git checkout -b nome-da-branch

_Coda, coda, coda mais um pouquinho_

>git add .

>git commit -m "Adiciona função de imprimir"

>git push

_Termina o objetivo do branch, e mergeia um pull request_

>git checkout main

>git pull













