# branch-feature-forking-workflow

Branch Feature Forking Workflow é uma mistura de Branch Feature Workflow com Forking Workflow.

Nova funcionalidade 

1. Primeira coisa devemos tirar um branch a partir da master no repositório oficial, isso pode ser feito inclusive pelo GitHub
![creating feature-1 branch](http://sc-cdn.scaleengine.net/i/a4338424388fdb37687dbf968097939f1.png)

2. Forke o projeto (caso você não tenha) 
![forking](http://sc-cdn.scaleengine.net/i/7da9034fb0a31dec0ef0b5c5c5e71dee.png)
![forkingTo](http://sc-cdn.scaleengine.net/i/321e1eb548cbd155f75ca969bf99ecbc.png)

3. Dado fork do projeto sob o seu usuário, você deve clonar seu o repositorio
```
git clone https://github.com/lfreneda/sample-bffw/
```

![clonning](http://sc-cdn.scaleengine.net/i/27a95a396b54a66fbc628e248d90560d.png)

4. é necessário também adicionar também uma referência para o repositorio official

```
git remote add official (endereco_repositorio_official)
```
![remoting](http://sc-cdn.scaleengine.net/i/91862c232dd14bc9b665376d1d2a4dc9.png)

5. Depois disso, voce deve criar sua branch de trabalho a partir da branch da funcionalidade (feature-1), vamos supor que uma das tasks para entregar a feature-1 é criar uma modelagem de classes, você então pode criar a branch feature-1-modelo-de-classes

![branching](http://sc-cdn.scaleengine.net/i/120af7bb5bf2668404b6bc335c4ad081.png)

Nesse momento nossas branchs estão com o ponteiro para o mesmo commit:

![graph-on-branching](http://sc-cdn.scaleengine.net/i/8e4fafeac8daff39819c2089dd57c638.png)

Vamos dizer que voce trabalhou nesse modelo de classes e após dois commits, voce já pode "integrar" essa task

git log

![history](http://sc-cdn.scaleengine.net/i/066996d969bf27788be46bb6d32aa88b.png)
![history-graph](http://sc-cdn.scaleengine.net/i/67bbdae1343a1a9a9e81317389b587a7.png)

Dado uma pequena contribuição "pronta", já é possível criar um pull request para o repositorio oficial. Para fazer isso é necessário empurrar suas alterações para seu repositorio

![1asdassda](http://sc-cdn.scaleengine.net/i/588eda2f950d81ebbf3040561a81110d.png)

Automaticamente ao acessar o repositorio do projeto voce vera ~Compare & pull request~

![compare-and-pull-request](http://sc-cdn.scaleengine.net/i/716240153e5b5d75564fc6dd52254434.png)

Importante lembrar que você deve selecionar como base fork a branch feature, no caso feature-1

![open-pull-request](http://sc-cdn.scaleengine.net/i/7bd847c3793d3bb34e9b0ad48126fd79.png)
