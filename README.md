# Guia de git para estudantes
Este é um guia básico e descontraído de _git_ feito por uma estudante para outros estudantes! 

:star:Se este guia lhe foi útil, ou você aprendeu a usar o _git_ comigo, deixa sua estrelinha como agradecimento!:star:

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
    
## 1. Como usar o _git_?
É importante mencionar que não abordarei neste guia a parte de instalação/ setup do _git_, e sim, o seu uso!

Ah, nós também faremos uso do git via linha de comando e não via aplicativo desktop.
### 1.1 Afinal, para que serve o git?
O git é um sistema de versionamento de código. Mas o que significa isso? Bem, sabe quando você está fazendo um trabalho e começa a salvar como versão1, versão2, versãofinal, versãofinalfinalagoravai, etc? Então, é tipo isso, só que direito.

Com isso, você consegue:
 - ter um controle muito bom de qualquer trabalho,
 - acompanhar a evolução,
 - ter a certeza de que pode voltar para uma parte do código que funciona caso você resolva fazer uma mudança que dê ruim (sem depender do crtl + z)
 - acesso ao código de vários computadores de forma facilitada
 - controle melhor de trabalhos em grupo

Eu prometo que depois que você aprender a usar o _git_, você não vai conseguir entender como as pessoas viviam antes dele.

### 1.2 Como salvar o código no _git?_ Também conhecido como _commit_
Primeiramente, o que é o _commit_? É mais ou menos o equivalente a salvar o seu código no _git_ (não no seu computador). 
Existem algumas regras para fazer isso da maneira a aproveitar melhor essa feature, as quais serão explicadas ao longo deste capítulo, mas vamos começar pelo comando de como fazer isso.

Se seu código está pronto para o _commit_, dê o comando:
>git status

Isso vai te mostrar se tem arquivos que foram modificados para serem "commitados". Se você modificou o arquivo, ele deve aparecer em vermelho no console.

![Image](https://github.com/user-attachments/assets/d21c151a-fdb4-4166-87f9-bdb9bec63c1c)

Agora você vai adicionar o que quer "commitar". Para adicionar todos os arquivos do projeto que foram modificados:
>git add .

Ou adicione somente um arquivo:
>git add nome_do_arquivo.py

Agora faça novamente o comando _git status_ e veja se os arquivos que você quer "commitar" ficaram verdinhos. Caso isso não tenha acontecido, provavelmente você não está na pasta certa na linha de comando. É preciso que os arquivos fiquem verdes para que sejam commitados.

![Image](https://github.com/user-attachments/assets/925fa1da-d1b5-416d-908a-9055bf64cf6a)

Agora vamos fazer o _commit_ propriamente dito.
  >git commit -m “Escreva aqui a mensagem do commit”

Você já "commitou", mas se você abrir o github no repositório do projeto, verá que sua mudança ainda não está aparecendo. Para que ela apareça, é preciso fazer o _push_:
  >git push

Agora sim, abra o github no repositório do projeto e verá que o seu código agora está aparecendo lá.

![Image](https://github.com/user-attachments/assets/4827202e-153f-4ff5-af72-45cec62e67ab)

## 1.3 Regras básicas de sobrevivência do _commit_
Para fazer o melhor aproveitamento do _commit_, existe uma série de dicas que facilitarão muito a sua vida, as quais serão brevemente explicadas abaixo.

#### 1.3.1 A primeira e mais importante dica

**Só faça commit de códigos que funcionem**. 

Assim, você consegue voltar para o último _commit_ caso faça alguma alteração que faça com que o código pare de funcionar.

#### 1.3.2 O que deve ter em um _commit_?
Para que um _commit_ seja super legível, o ideal é que você faça somente **uma coisa em cada um**.

Evite fazer um _commit_ que implemente uma função em um arquivo, modifique a formatação do código em outro, e remova comentários em um terceiro. Pois dessa forma, quando você for ver o _commit_ pelo github, terão mil alterações em mil arquivos diferentes, e ficará mais difícil achar a alteração importante que realmente foi o ponto alto do _commit_.

Então se quiser fazer essas três coisas mencionadas no exemplo, faça:
 - Um _commit_ para implementar a função
 - Um para corrigir a formatação
 - Um para remover comentários

#### 1.3.3 Padrões de mensagem de _commit_
Sempre começar a mensagem com a primeira letra em maiúsculo, no tempo verbal imperativo afirmativo, ou seja, é como se fosse uma resposta à pergunta: o que este _commit_ faz? 
As mensagens não devem ter ponto final.

**Exemplos:**

![Image](https://github.com/user-attachments/assets/862be7da-a4a8-4ffd-bbd1-9ea0b498e121)

A língua utilizada para os _commits_ depende do projeto. Sempre combine com seus colegas qual será a utilizada para não ficar misturado.

Evitar commits genéricos e imprecisos como: 
- Faz pequenas alterações (quais?),
- Arruma bugs (que bugs?)
- Mexe na função imprimir (tá, mas o que foi mudado?)

A boa prática é sempre fazer _commits_ façam só a mensagem do _commit_ diz.

**Anti-exemplos**
Abaixo são mostrados alguns exemplos de como **não fazer _commits_** e os problemas com eles:

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
  -  Só "commite" códigos que funcionem
  -  Só mexa em _uma coisa_ específica em cada _commit_
  -  Dê nomes que digam exatamente o que você fez naquele _commit_
    -  Resposta à pergunta: o que este _commit_ faz?
    -  Sempre na mesma língua (ou tudo em português ou tudo em inglês)
    -  Primeira letra em maiúsculo
    -  Sem pontuação no final

### 1.5 Resumo comandos _commit_
> git add .

> git commit -m "Cria função remover"

> git push
  
## 2. Uso de _branches_
Se você reparou que para trabalhos em grupo, estava sendo um pouco complicado usar o _git_, pois você e seus colegas tinham que avisar quando estavam mexendo no projeto, e volta e meia alguém não avisava e acabava gerando confusão, seus problemas acabaram!

### 2.1 O que são _branches_?
_Branches_ são derivações do código utilizados, normalmente, para adicionar novas funções ao programa. Ao utilizar _branches_, vários programadores podem trabalhar em um mesmo código ao mesmo tempo, ficando mais simples de resolver conflitos (diferenças entre os códigos). 

Mesmo quando se está trabalhando sozinho num código, esta é uma prática que é recomendada. Por exemplo: 

Imagine que você está construindo uma aplicação web e começa a implementação de uma nova função, mas acaba descobrindo que ela é mais complicada do que o esperado. O que você faz? Fica preso nela? Comenta parte do código?

Na realidade o mais fácil é você trabalhar nessa nova função em um novo _branch_. Assim, você pode apenas deixar esse _branch_ interminado e abre outro para continuar o projeto até você ter a capacidade de voltar para esta parte.

Assim você continua com a main sempre funcionando sem precisar comentar parte do código para poder rodar.

Vamos mostrar agora com imagens para ficar mais claro!
Na imagem 1, os alunos Ana, Giovanni e Gustavo tem uma versão da _Main_ (código base) nos seus respectivos computadores e cada um ficou responsável por adicionar uma nova função ao programa. 

Cada um clonou o repositório do projeto localmente, e estão inicialmente no _branch main_. 

Para que cada um comece a lidar com a sua parte do projeto, a primeira coisa que devem fazer é criar _branches_. 

![Image](https://github.com/user-attachments/assets/23deaf28-bcf0-4ec9-a966-42548fbec4ad)

### 2.2 Como criar _branches_?
Na linha de comando, digite: 

  >git checkout -b nome-da-branch

Este comando troca de _branch_ já criando um branch novo. Observe que o padrão para nomes de _branches_ é ser tudo em minúsculo e com traços no lugar de espaços.

### 2.3 Como trocar de _branches_?

  >git checkout nome-da-branch

### 2.4 Como saber em qual _branch_ estou?

  >git status

### 2.5 Como ver os _branches_ no github?
Entre no repositório, e embaixo do nome do repositório irá mostrar o nome do branch. Na página inicial geralmente é o _branch main_ que aparece. Clique nele e em seguida em view all branches.

![Image](https://github.com/user-attachments/assets/1ca4246b-ee7d-41c0-8a5f-c55c40ecd152)

Para deletar um _branch_, é só fazer este procedimento e clicar na lixeira. Depois de fazer o merge, ou caso desista de trabalhar neste branch, ele deve ser deletado.

### 2.6 Procedimento _merge/ pull request_
Você termina a parte do código em que estava trabalhando, realiza os testes, _verifica que tudo funciona direitinho_. Então é hora de juntar a sua parte com a base do projeto (_main_). 
- Primeiro: execute todos os passos do [Como salvar o código no git? Também conhecido como commit](#12-como-salvar-o-codigo-no-git-também-conhecido-como-commit).
- Apenas na primeira vez que fizer o _push_, você tem que dar o seguinte comando:
>git push --set-upstream origin nome-da-branch
- Avise a todos os colegas de equipe que irá abrir um PR (_pull request_)
- Abra o github no repositório do projeto e você verá uma mensagem em uma cor chamativa e com um botão ao lado escrito “_compare & pull request_”. Clique nele.

<img width="740" alt="Image" src="https://github.com/user-attachments/assets/f0a30448-dd96-4fc3-a7cd-54c47c97ed36" />


Ou entre no _branch_ e faça por lá.


<img width="741" alt="Image" src="https://github.com/user-attachments/assets/9b5cbe7c-86b1-4313-b038-40b0a063d304" />

  Preencha todos os campos do _pull request_ de maneira clara.
- Dê um assign para que outro membro da equipe verifique se o seu _pull request_ está ok para ser mergeado (você também pode auto-aprovar seu PR se quiser)
- Após a aprovação do PR por você ou por um colega, siga com os passos que serão descritos logo mais.

Primeiro é interessante você saber que ao mergear um PR, o seu _branch main_ local _não será automaticamente atualizado_. 

Após o PR "mergeado":

Volte para o _branch main_:
  
>git checkout main

Confira se está na _main_ com:

>git status

Atualize a sua _main_ local com:

>git pull

- Delete o _branch_ no github

<img width="731" alt="Image" src="https://github.com/user-attachments/assets/73619bf8-5a21-4397-8ed0-f7641762ff9e" />

- Avisar a todos da equipe que mergeou um novo PR, para que todos façam _pull_ na _main_.
### 2.7 Comecei a alterar o código mas esqueci de criar um branch!

>git checkout -b nome-da-branch

Este comando irá levar suas alterações para este novo _branch._
### 2.8 Fiz _push_ na _Main_!!
Quando se faz isso, você pula o verificador de _merge_ do github, que verifica antes de fazer o _merge_ se não há conflitos com a main. Isso poderá causar diversos problemas e seus colegas de trabalho _não ficarão nenhum pouco felizes._ Por isso é sempre importante: **antes de começar a codar, dê o comando _git status_ para saber onde está e crie sua branch.** É possível bloquear o _push_ direto na _main_ pelas configurações do repositório no github, e isso é uma prática recomendada.
### 2.9 Procedimento rebase
_Rebase_ faz exatamente o que o nome diz: troca a base. E o que é a base? É a _main_. Quando uma pessoa faz um _merge_ na _main_, essa main não é automaticamente atualizada. Pelo contrário, todo mundo continua com o _branch_ antigo (antes do _merge_) em seus computadores. Isso nem sempre é um problema.  

No exemplo abaixo (imagem 2), todos os programadores estão trabalhando em uma parte do código independente uma da outra. Logo, não há necessidade de atualizarem as suas bases, é só cada um fazer um _merge_ que dará tudo certo.

![Image](https://github.com/user-attachments/assets/ea0a1db9-c0ee-4d5c-b47a-6c52ce2495f5)

É sempre bom saber que quando um membro da equipe faz um _merge_, a _main_ é atualizada no github, mas não é automaticamente atualizada nos computadores de cada membro da equipe, como é mostrado na imagem 3.

![Image](https://github.com/user-attachments/assets/83d6340f-bdd6-4f93-b8b3-3632bb0fc4b7)

Vamos dizer que no exemplo da imagem 3, Giovanni não precisa saber como a Ana fez a função “remover” para terminar a sua parte do código. Então não há problemas em ele não atualizar sua _main_ dentro do seu _branch_ (embora ele deva mudar para o _branch main_, fazer o _pull_ e depois voltar para o _branch_ no qual estava trabalhando) , ele deva fazer isso, como descrito no [Procedimento merge/pull request](#26-procedimento-merge-e-pull-request)). 

Já Gustavo prefere saber como Ana fez, já que a função na qual está trabalhando - inserir - é um pouco parecida, então ele opta por fazer o rebase e continuar o trabalho a partir disso. Em sua branch ele dá o seguinte comando:

>git rebase main

Esse comando irá trocar a _main_ do _branch_ pela atualizada. Após esse comando, podem aparecer muitos conflitos com o seu código. Caso nenhum problema aconteça, dê o comando:

>git rebase --continue

Caso aconteçam conflitos, resolva-os primeiro, e depois dê o comando mencionado anteriormente. Ou, caso queira desistir do rebase, dê o comando:

>git rebase --abort

Quando for fazer o _push_, será necessário fazer:

>git push --f

O _git rebase_ reescreve o histórico de _commits_ (muda o _hash_ dos _commits_). Então, depois de um _rebase_, o seu _branch_ local fica diferente da que está no repositório remoto. Por isso é necessário usar o _push force (git push --f)_. 

Em uma empresa, você vai demorar para ter permissão pra usar esse comando, mas em trabalhos da faculdade dá para usar. 

**Não é necessário fazer _commit_ após fazer o _rebase_.**

E assim ficou a visão de Gustavo da _main_ após o _rebase_:

![Image](https://github.com/user-attachments/assets/72f80711-fbdf-4e6b-8ae3-ad058e836686)

### 2.10 Você pode entrar no _branch_ dos amiguinhos
Se seu colega já tiver feito _push_ no _branch_ dele, basta você fazer os seguintes comandos caso queira entrar neste _branch_:
>git checkout main
>git pull
>git checkout nome-do-branch-do-coleguinha

### 2.11 Resumo comandos _branch_
>git checkout -b nome-da-branch

_Coda, coda, coda mais um pouquinho_

>git add .

>git commit -m "Adiciona função de imprimir"

>git push

_Termina o objetivo do branch, e mergeia um pull request_

>git checkout main

>git pull













