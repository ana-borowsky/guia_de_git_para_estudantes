# Guia de git para estudantes
Este é um guia básico e descontraído de git feito por uma estudante, para outros estudantes. Este guia estará em constante evolução, e irá começar abordando como lidar com branches.

Como eu já ensinei várias pessoas a utilizarem o git, achei que pudesse deixar público para que pudesse ser mais útil para mais gente. 

**Se este guia lhe foi útil, ou você aprendeu a usar o git comigo, deixa sua estrelinha como agradecimento!**

## 1. Uso de branches
### 1.1 O que são branches?
Branches são derivações do código utilizados, normalmente, para adicionar novas funções ao programa. Ao utilizar branches, vários programadores podem trabalhar em um mesmo código ao mesmo tempo, ficando mais simples de resolver conflitos (diferenças entre os códigos). 

Mesmo quando se está trabalhando sozinho num código, esta é uma prática que pode ser recomendada em alguns casos. Por exemplo, se você está construindo uma aplicação web, começa a implementação de uma nova função, e ela é mais complicada do que você esperava que ela fosse, então você decide começar outra parte do projeto antes de terminar essa. Você pode ter uma branch para cada uma e está tudo certo. Assim você continua com a main sempre funcionando sem precisar comentar parte do código para poder rodar.

No da imagem 1, Ana, Giovanni e Gustavo tem uma versão da Main (código base) nos seus respectivos computadores e cada um ficou responsável por adicionar uma nova função ao programa. <br>
![Image](https://github.com/user-attachments/assets/23deaf28-bcf0-4ec9-a966-42548fbec4ad)<br><br>

### 1.2 Como criar branches?
Na linha de comando, digite: 
  _git checkout -b nome-da-branch_

Este comando troca de branch já criando uma branch nova. Observe que o padrão para nomes de branches é ser tudo em minúsculo e com traços no lugar de espaços.

### 1.3 Como trocar de branches?
  _git checkout nome-da-branch_

### 1.4 Como saber em qual branch estou?
  _git status_

### 1.5 Procedimento de commit
Primeiramente, só faça commit de códigos que estão funcionando. Assim, você consegue voltar para o último commit caso faça algo de muito errado, você sempre volta para uma versão do código que funciona.
  _git add . (ou o nome do arquivo)_
Sempre dê um git status para conferir se o que você quis adicionar realmente foi adicionado
  _git commit -m “Adiciona função inserir”_
  _git push_

A primeira vez (e só ela, o restante é normal (_git push_)) que fizer push para uma branch, o comando será:
  _git push --set-upstream origin nome-da-branch_

Observe que o padrão do commit é sempre ser com a primeira letra em maiúsculo, no tempo verbal imperativo afirmativo - ou seja, é como se fosse uma resposta à pergunta: o que este commit faz? - e sem ponto final.

A língua utilizada para os commits depende do projeto. Sempre combine com seus colegas qual será a utilizada para não ficar misturado.

Evitar commits genéricos e imprecisos como: Faz pequenas alterações (quais?), arruma bugs (que bugs?), etc. A boa prática é sempre fazer pequenos commits que sempre tenham o nome condizente exatamente com o que foi feito.

### 1.6 Como ver os branches no github?
Entre no repositório, e embaixo do nome do repositório irá mostrar o nome da branch. Na página inicial geralmente é o branch main que aparece. Clique nele e em seguida em view all branches.<br>
![Image](https://github.com/user-attachments/assets/1ca4246b-ee7d-41c0-8a5f-c55c40ecd152)<br><br>

Para deletar um branch, é só fazer este procedimento e clicar na lixeira. Depois de fazer o merge, ou caso desista de trabalhar neste branch, ele deve ser deletado.

### 1.7 Procedimento merge/ pull request
Você termina a parte do código em que estava trabalhando, realiza os testes, verifica que tudo funciona direitinho. Então é hora de juntar a sua parte com a base do projeto (main). 
1. Primeiro: execute todos os passos do procedimento de commit.
2. Avise a todos os colegas de equipe que irá abrir um PR (pull request)
3. Abra o github no repositório do projeto e você verá uma mensagem em uma cor chamativa e com um botão ao lado escrito “compare & pull request”. Clique nele.








