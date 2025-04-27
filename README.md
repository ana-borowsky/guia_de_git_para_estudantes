# Guia de git para estudantes
Este é um guia básico e descontraído de git feito por uma estudante para outros estudantes. Este guia estará em constante evolução, e irá começar abordando como lidar com branches.

Como eu já ensinei várias pessoas a utilizarem o git, achei que pudesse deixar público para que pudesse ser mais útil para mais gente. 

:star:Se este guia lhe foi útil, ou você aprendeu a usar o git comigo, deixa sua estrelinha como agradecimento!:star:

## Índice
- [Uso de branches](#1-uso-de-branches)
  - [O que são branches?](#o-que-são-branches)
  - [Como criar branches?](#como-criar-branches)
  - [Como trocar de branches?](#como-trocar-de-branches)
  - [Como saber em qual branch estou?](#como-saber-em-qual-branch-estou)
  - [Procedimento de commit](#procedimento-de-commit)
  - [Como ver os branches no GitHub?](#como-ver-os-branches-no-github)
  - [Procedimento merge/pull request](#procedimento-mergepull-request)
  - [Comecei a alterar o código mas esqueci de criar uma branch, o que eu faço?](#comecei-a-alterar-o-codigo-mas-esqueci-de-criar-uma-branch-o-que-eu-faco)
  - [Fiz push na Main, o que eu faço?](#fiz-push-na-main-o-que-eu-faco)
  - [Procedimento rebase](#procedimento-rebase)
    
## 1. Uso de branches
### 1.1 O que são branches?
Branches são derivações do código utilizados, normalmente, para adicionar novas funções ao programa. Ao utilizar branches, vários programadores podem trabalhar em um mesmo código ao mesmo tempo, ficando mais simples de resolver conflitos (diferenças entre os códigos). 

Mesmo quando se está trabalhando sozinho num código, esta é uma prática que pode ser recomendada em alguns casos. Por exemplo, se você está construindo uma aplicação web, começa a implementação de uma nova função, e ela é mais complicada do que você esperava que ela fosse, então você decide começar outra parte do projeto antes de terminar essa. Você pode ter uma branch para cada uma e está tudo certo. Assim você continua com a main sempre funcionando sem precisar comentar parte do código para poder rodar.

No da imagem 1, Ana, Giovanni e Gustavo tem uma versão da Main (código base) nos seus respectivos computadores e cada um ficou responsável por adicionar uma nova função ao programa. 

![Image](https://github.com/user-attachments/assets/23deaf28-bcf0-4ec9-a966-42548fbec4ad)

### 1.2 Como criar branches?
Na linha de comando, digite: 
  >git checkout -b nome-da-branch

Este comando troca de branch já criando uma branch nova. Observe que o padrão para nomes de branches é ser tudo em minúsculo e com traços no lugar de espaços.

### 1.3 Como trocar de branches?
  >git checkout nome-da-branch

### 1.4 Como saber em qual branch estou?
  >git status

### 1.5 Procedimento de commit
Primeiramente, só faça commit de códigos que estão funcionando. Assim, você consegue voltar para o último commit caso faça algo de muito errado, você sempre volta para uma versão do código que funciona.
  >git add . (ou o nome do arquivo)

Sempre dê um git status para conferir se o que você quis adicionar realmente foi adicionado

  >git commit -m “Adiciona função inserir”
  >git push

A primeira vez (e só ela, o restante é normal (_git push_)) que fizer push para uma branch, o comando será:<br>
  >git push --set-upstream origin nome-da-branch

Observe que o padrão do commit é sempre ser com a primeira letra em maiúsculo, no tempo verbal imperativo afirmativo - ou seja, é como se fosse uma resposta à pergunta: o que este commit faz? - e sem ponto final.

A língua utilizada para os commits depende do projeto. Sempre combine com seus colegas qual será a utilizada para não ficar misturado.

Evitar commits genéricos e imprecisos como: Faz pequenas alterações (quais?), arruma bugs (que bugs?), etc. A boa prática é sempre fazer pequenos commits que sempre tenham o nome condizente exatamente com o que foi feito.

### 1.6 Como ver os branches no github?
Entre no repositório, e embaixo do nome do repositório irá mostrar o nome da branch. Na página inicial geralmente é o branch main que aparece. Clique nele e em seguida em view all branches.

![Image](https://github.com/user-attachments/assets/1ca4246b-ee7d-41c0-8a5f-c55c40ecd152)

Para deletar um branch, é só fazer este procedimento e clicar na lixeira. Depois de fazer o merge, ou caso desista de trabalhar neste branch, ele deve ser deletado.

### 1.7 Procedimento merge/ pull request
Você termina a parte do código em que estava trabalhando, realiza os testes, verifica que tudo funciona direitinho. Então é hora de juntar a sua parte com a base do projeto (main). 
1. Primeiro: execute todos os passos do procedimento de commit.
2. Avise a todos os colegas de equipe que irá abrir um PR (pull request)
3. Abra o github no repositório do projeto e você verá uma mensagem em uma cor chamativa e com um botão ao lado escrito “compare & pull request”. Clique nele.<br><br>

<img width="740" alt="Image" src="https://github.com/user-attachments/assets/f0a30448-dd96-4fc3-a7cd-54c47c97ed36" />


Ou entre no branch e faça por lá.


<img width="741" alt="Image" src="https://github.com/user-attachments/assets/9b5cbe7c-86b1-4313-b038-40b0a063d304" />

  Preencha todos os campos do pull request de maneira clara.
4. Dê um assign para que outro membro da equipe verifique se o seu pull request está ok para ser mergeado
5. Após a aprovação do PR por um colega, siga com os comandos:
>git checkout main
>git status (conferir se está na main)
>git pull_
6. Deletar o branch no github

<img width="731" alt="Image" src="https://github.com/user-attachments/assets/73619bf8-5a21-4397-8ed0-f7641762ff9e" />

7. Avisar a todos da equipe que mergeou um novo PR, para que todos façam pull na main.
### 1.8 Comecei a alterar o código mas esqueci de criar uma branch, o que eu   faço?
>git checkout -b nome-da-branch
Este comando irá levar suas alterações para esta nova branch.
### Fiz push na Main, o que eu faço?
Quando se faz isso, você pula o verificador de merge do github, que verifica antes de fazer o merge se não há conflitos com a main. Isso poderá causar diversos problemas e seus colegas de trabalho _não ficarão nenhum pouco felizes._ Por isso é sempre **importante: antes de começar a codar, dê o comando git status para saber onde está e crie sua branch.** É possível bloquear o push direto na main pelas configurações do repositório no github, e isso é uma prática recomendada.
### 1.10 Procedimento rebase
Rebase faz exatamente o que o nome diz: troca a base. Quando uma pessoa faz um merge na main, essa main não é automaticamente atualizada. Pelo contrário, todo mundo continua com a branch antiga (antes do merge) em seus computadores. Isso nem sempre é um problema.  No exemplo abaixo (imagem 2), todos os programadores estão trabalhando em uma parte do código independente uma da outra. Logo, não há necessidade de atualizarem as suas bases, é só cada um fazer um merge que dará tudo certo.

![Image](https://github.com/user-attachments/assets/ea0a1db9-c0ee-4d5c-b47a-6c52ce2495f5)

É sempre bom saber que quando um membro da equipe faz um merge, a main é atualizada no github, mas não nos computadores de cada membro da equipe, como é mostrado na imagem 3.

![Image](https://github.com/user-attachments/assets/83d6340f-bdd6-4f93-b8b3-3632bb0fc4b7)

Vamos dizer que no exemplo da imagem 3, Giovanni não precisa saber como a Ana fez a função “remover” para terminar a sua parte do código. Então não há problemas em ele não atualizar sua main dentro de sua branch (embora no seu computador, ele deva fazer isso, como descrito no tópico “merge” deste manual). Já Gustavo prefere saber como Ana fez, já que a função na qual está trabalhando - inserir - é um pouco parecida, então ele opta por fazer o rebase e continuar o trabalho a partir disso. Em sua branch ele dá o seguinte comando:

>git rebase main

Esse comando irá trocar a main da branch pela atualizada. Após esse comando, podem aparecer muitos conflitos com o seu código. Caso nenhum problema aconteça, dê o comando:

>git rebase --continue

Caso aconteçam conflitos, resolva-os primeiro, e depois dê o comando mencionado anteriormente. Ou, caso queira desistir do rebase, dê o comando:

>git rebase --abort

Quando for fazer o push, será necessário fazer:

>git push --f

O git rebase reescreve o histórico de commits (muda o hash dos commits). Então, depois de um rebase, a sua branch local fica diferente da que está no repositório remoto. Por isso é necessário usar o push force. Em uma empresa, você vai demorar para ter clearance pra usar esse comando, mas em trabalhos da faculdade, está tudo bem.
**Não é necessário fazer commit após fazer o rebase.**













