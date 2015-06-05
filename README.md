# Branch Feature Forking Workflow

Branch Feature Forking Workflow é uma mistura de Branch Feature Workflow com Forking Workflow.

* [Sumário]
  * [Nova funcionalidade](#nova-funcionalidade)
  * [Forking](#forking)
  * [Clonando o repositório](#clonando-o-repositório)
  * [Iniciando o desenvolvimento da feature](#iniciando-o-desenvolvimento-da-feature)
  * [Contribuindo](#contribuindo)
  * [Contribuição aceita pelo time](#contribuição-aceita-pelo-time)
  * [Atualizando seu repositório](#atualizando-seu-repositório)
  * [Feature em produção](#feature-em-produção)
  * [Limpeza](#limpeza)
  
## Nova funcionalidade

Dado uma nova funcionalidade é necessário que a mesma seja criado no repositório oficial do projeto, isso pode ser feito pelo command line ou pelo próprio GitHub

Vamos supor que nossa funcionalidade se chamará __feature-1__

![creating feature-1 branch](http://sc-cdn.scaleengine.net/i/a4338424388fdb37687dbf968097939f1.png)

## Forking

Caso você não tenha o projeto sob seu usuário, é necessário forkar o projeto.
Esse procedimento também pode ser feito pelo próprio GitHub, basta acessar o repositório oficial e clicar no botão __Fork__ (lado direito superior da tela).

![forking](http://sc-cdn.scaleengine.net/i/7da9034fb0a31dec0ef0b5c5c5e71dee.png)

![forkingTo](http://sc-cdn.scaleengine.net/i/321e1eb548cbd155f75ca969bf99ecbc.png)

## Clonando o repositório

Dado que você tem o fork do projeto sob seu usuário, você deve clonar o repositório

![clonning](http://sc-cdn.scaleengine.net/i/27a95a396b54a66fbc628e248d90560d.png)

É necessário também adicionar também uma referência para o repositorio oficial, usaremos esse apontamento para receber alterações do projeto oficial, temos que sempre ter isso sempre como mindset, sempre vamos se atualizar com o repositório oficial. Pode ser que alguma outra funcionalidade foi integrada ao projeto principal ou pode ser que alguma correção (hotfix) tenha sido encontrado e solucinado.

![remoting](http://sc-cdn.scaleengine.net/i/91862c232dd14bc9b665376d1d2a4dc9.png)

Nosso repositório terá dois apontamentos

Alias | Descrição
------------ | -------------
origin | nome *padrão*, aponta para o repositório padrão (no caso, o sob o seu usuário)
official | aponta para o repositório oficial do projeto

## Iniciando o desenvolvimento da feature

Agora você tem todo repositório pronto, hora de começar a escrever lindas linhas de código, certo?

Você deve criar uma branch a partir da branch da funcionalidade (no nosso caso, __feature-1__).
Vamos supor que uma das tasks para entregar a __feature-1__ é criar uma modelagem de classes. 

Você pode criar a branch feature-1-modelo-de-classes

![branching](http://sc-cdn.scaleengine.net/i/120af7bb5bf2668404b6bc335c4ad081.png)

Nesse momento nossas branchs estão com o ponteiro para o mesmo commit, teremos a seguinte árvore: 

![graph-on-branching](http://sc-cdn.scaleengine.net/i/8e4fafeac8daff39819c2089dd57c638.png)

## Contribuindo

Vamos dizer que voce trabalhou no modelo de classes da __feature-1__ e após (*dois*) commits, você já pode "contribuir" para a funcinalidade __feature-1__.

![git-log](http://sc-cdn.scaleengine.net/i/066996d969bf27788be46bb6d32aa88b.png)

![history-graph](http://sc-cdn.scaleengine.net/i/67bbdae1343a1a9a9e81317389b587a7.png)

Dado uma pequena contribuição "pronta", já é possível criar um pull request para o repositorio oficial. 
Para fazer isso é necessário *empurrar* suas alterações

![git-push](http://sc-cdn.scaleengine.net/i/588eda2f950d81ebbf3040561a81110d.png)

Automaticamente depois do __git push__, quando acessar o repositorio do oficial projeto voce verá um botão verde __Compare & pull request__

![compare-and-pull-request](http://sc-cdn.scaleengine.net/i/716240153e5b5d75564fc6dd52254434.png)

__Importante lembrar que você deve selecionar como base fork a branch feature, no caso feature-1*__

![open-pull-request](http://sc-cdn.scaleengine.net/i/7bd847c3793d3bb34e9b0ad48126fd79.png)

Pull request criado, será avaliado pelo time.

*Caso seja rejeitado, é necessário fechar o pull request, basicamente o que você tem que fazer é implementar as correções e criar outro pull request posteriormente.*

## Contribuição aceita pelo time

Time deve avaliar questões de design, coding conventions/standards, testes de unidade entre outros..

Ao aceitar um pull request pode se aproveitar e deletar a branch remota com a alteração, isso é feito pelo botão __Delete branch__.

![delete-branch](http://sc-cdn.scaleengine.net/i/ec4e5b2155d715702bb158d1a41b1b3f1.png)

## Atualizando seu repositório

Caso seja aceito, é necessário atualizar sua branch com as novas contribuções, na verdade, essa prática deve ser frequentemente feita pelos membros da equipe em suas branchs "interessadas". 

Grafico localmente antes de atualizar com as alteracoes do servidor

![graph-antes-atualizacao](http://sc-cdn.scaleengine.net/i/53ee710e0608dc430f1c4bad82ab3729.png)

(falar do prune)

![ci](http://sc-cdn.scaleengine.net/i/2d6e97349b042ccd48d2b33f6d529a20.png)

TA-DA :tada:

![graph](http://sc-cdn.scaleengine.net/i/917d3fd475bc4cf2cd582ba80599a86c.png)

Você também pode/deve limpar localmente as branchs que você ja integrou.

![branch-d](http://sc-cdn.scaleengine.net/i/b8089b83d3cd56f439393e685abe81c9.png)

## Feature em produção

Novas contribuições/pull requests serão feitos assim como o anterior, gerando uma arvore parecida com a seguinte:

![graph-2](http://sc-cdn.scaleengine.net/i/9ab852bdd2f3358e733ad41e3b1fad14.png)

Então, foram feitos 2 pull request para conclusão da feature-1, Dado que a feature já está pronta para ser coloca em produção, é possível fazer isso diretamente pelo GitHub

(efeito cascata)

![master-feature-1-pr](http://sc-cdn.scaleengine.net/i/c00a173a81e7bd1174d4a0ce690ffa57.png)

Done :)

Dado o PR da feature-1 para a master e o merge, temos que atualizar a nosso repositorio com a versao atual, esse procedimento é bem parecido com o anterior

## Limpeza

![atualizando-ambiente](http://sc-cdn.scaleengine.net/i/b741f6f212cbfda51f88909a4d985ef0.png)

Teremos um graph parecido com esse: 

![graph-feature-1](http://sc-cdn.scaleengine.net/i/35ee1713c32981fcd7d1ef97d7c0dc80.png)

E podemos limpar nossas branchs localmente e remotamente

local

![cleaning-local-branch](http://sc-cdn.scaleengine.net/i/413c5d8775ca3cfbf9b0de11bb2767ed.png)

remoto

![cleaning-remote-branch](http://sc-cdn.scaleengine.net/i/641375177ccf945b25db2f90159013eb.png)

Também é preciso deletar a branch feature-1 que está sob seu usuario/repositorio, infelizmente o GitHub não limpa essa branch =(

![cleaning-remote-branch-user](http://sc-cdn.scaleengine.net/i/6c3e745ebb15761df05d8d13bb78886c.png)

No final da limpeza teremos uma arvore parecida com a seguinte:

![graph-feature-merge](http://sc-cdn.scaleengine.net/i/9cde591cce1383454cbd45c63a0a2df3.png)

Note que o ponteiro da origin/master está desatualizado, isso é verdade, pois acabamos não usando para nada, não necessariamente, mas como opçao, voce pode sincornizar sua master sob seu usuario :)

![master-user](http://sc-cdn.scaleengine.net/i/a0767d8210c0952400aa4c6dd8431f3a.png)

E finalmente, a arvore:

![graph-ufa](http://sc-cdn.scaleengine.net/i/8062ec97f356cc1692ee3792b3834a5f.png)
