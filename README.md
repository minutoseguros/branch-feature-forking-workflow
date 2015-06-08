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

![creating feature-1 branch](https://raw.githubusercontent.com/lfreneda/branch-feature-forking-workflow/master/images/1-creating-branch-github.png)

## Forking

Caso você não tenha o projeto sob seu usuário, é necessário forkar o projeto.
Esse procedimento também pode ser feito pelo próprio GitHub, basta acessar o repositório oficial e clicar no botão __Fork__ (lado direito superior da tela).

![forking](https://raw.githubusercontent.com/lfreneda/branch-feature-forking-workflow/master/images/2-forking-button.png)

![forkingTo](https://raw.githubusercontent.com/lfreneda/branch-feature-forking-workflow/master/images/3-forking-to.png)

## Clonando o repositório

Dado que você tem o fork do projeto sob seu usuário, você deve clonar o repositório

![clonning](https://raw.githubusercontent.com/lfreneda/branch-feature-forking-workflow/master/images/4-cloning-commandline.png)

É necessário também adicionar também uma referência para o repositorio oficial, usaremos esse apontamento para receber alterações do projeto oficial, temos que sempre ter isso sempre como mindset, sempre vamos se atualizar com o repositório oficial. Pode ser que alguma outra funcionalidade foi integrada ao projeto principal ou pode ser que alguma correção (hotfix) tenha sido encontrado e solucinado.

![remoting](https://raw.githubusercontent.com/lfreneda/branch-feature-forking-workflow/master/images/5-remote-add-official.png)

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

![branching](https://raw.githubusercontent.com/lfreneda/branch-feature-forking-workflow/master/images/6-creating-branch-feature.png)

Nesse momento nossas branchs estão com o ponteiro para o mesmo commit, teremos a seguinte árvore: 

![graph-on-branching](https://raw.githubusercontent.com/lfreneda/branch-feature-forking-workflow/master/images/7-graph-after-branch-feature-created.png)

## Contribuindo

Vamos dizer que voce trabalhou no modelo de classes da __feature-1__ e após (*dois*) commits, você já pode "contribuir" para a funcinalidade __feature-1__.

![git-log](https://raw.githubusercontent.com/lfreneda/branch-feature-forking-workflow/master/images/8-git-log.png)

![history-graph](https://raw.githubusercontent.com/lfreneda/branch-feature-forking-workflow/master/images/9-graph-after-commitin.png)

Dado uma pequena contribuição "pronta", já é possível criar um pull request para o repositorio oficial. 
Para fazer isso é necessário *empurrar* suas alterações

É uma boa prática sempre atualizar seu repositório antes de enviar uma contribuição, pode ser que algum pull request foi integrado ou em produção ou na branch feature.

![ci](https://raw.githubusercontent.com/lfreneda/branch-feature-forking-workflow/master/images/15-updated-local-repository.png)

![git-push](https://raw.githubusercontent.com/lfreneda/branch-feature-forking-workflow/master/images/10-pushing-feature-commits.png)

Automaticamente depois do __git push__, quando acessar o repositorio do oficial projeto voce verá um botão verde __Compare & pull request__

![compare-and-pull-request](https://raw.githubusercontent.com/lfreneda/branch-feature-forking-workflow/master/images/11-compare-and-pull-request.png)

__Importante lembrar que você deve selecionar como base fork a branch feature, no caso feature-1*__

![open-pull-request](https://raw.githubusercontent.com/lfreneda/branch-feature-forking-workflow/master/images/12-open-pull-request.png)

Pull request criado, será avaliado pelo time.

*Caso seja rejeitado, é necessário fechar o pull request, basicamente o que você tem que fazer é implementar as correções e criar outro pull request posteriormente.*

## Contribuição aceita pelo time

Time deve avaliar questões de design, coding conventions/standards, testes de unidade entre outros..

Ao aceitar um pull request pode se aproveitar e deletar a branch remota com a alteração, isso é feito pelo botão __Delete branch__.

![delete-branch](https://raw.githubusercontent.com/lfreneda/branch-feature-forking-workflow/master/images/13-pull-request-acepted-delete-branch.png)

## Atualizando seu repositório

Atualizar sempre o repositório é uma boa prática.
Sempre que possível e obrigatóriamente após ter um pull request integrado deve se atualizar suas branchs __interessadas__.

Continuando na __feature-1__, temos a seguinte árvore quando fizemos nosso pull request

![graph-antes-atualizacao](https://raw.githubusercontent.com/lfreneda/branch-feature-forking-workflow/master/images/14-graph-feature-commited.png)

![ci](https://raw.githubusercontent.com/lfreneda/branch-feature-forking-workflow/master/images/15-updated-local-repository.png)

Após a atualização das branchs __interessadas__, teremos a seguinte árvore:

![graph](https://raw.githubusercontent.com/lfreneda/branch-feature-forking-workflow/master/images/16-graph-local-repository-updated.png)

Você também pode/deve limpar localmente as branchs que você ja integrou.

![branch-d](https://raw.githubusercontent.com/lfreneda/branch-feature-forking-workflow/master/images/17-cleaning-delete-local-branch.png)

## Feature em produção

Vamos dizer que tivemos duas contribuições na __feature-1__.
Novas contribuições/pull requests serão feitos assim como o anterior, gerando uma arvore parecida com a seguinte:

![graph-2](https://raw.githubusercontent.com/lfreneda/branch-feature-forking-workflow/master/images/18-graph-feature-in-production.png)

Dado que a __feature-1__ já está pronta para ser coloca em produção, criaremos um pull request no próprio repositório oficial. Podemos fazer isso pelo GitHub

![master-feature-1-pr](https://raw.githubusercontent.com/lfreneda/branch-feature-forking-workflow/master/images/19-compare-and-pull-request.png)

## Limpeza

Depois que o pull request da funcionlidade completa (__feature-1__) para a __master__ e o merge, precisamos atualizar a nosso repositorio com a versão __master__ atual, esse procedimento é bem parecido com o [anterior](#atualizando-seu-repositório)

![atualizando-ambiente](https://raw.githubusercontent.com/lfreneda/branch-feature-forking-workflow/master/images/20-cleaning-remote-prune.png)

Teremos um graph parecido com esse: 

![graph-feature-1](https://raw.githubusercontent.com/lfreneda/branch-feature-forking-workflow/master/images/21-merge-with-master.png)

E podemos limpar nossas branchs localmente e remotamente

![cleaning-local-branch](https://raw.githubusercontent.com/lfreneda/branch-feature-forking-workflow/master/images/22-delete-local-feature.png)
![cleaning-remote-branch](https://raw.githubusercontent.com/lfreneda/branch-feature-forking-workflow/master/images/23-prune-remote-official.png)
![cleaning-remote-branch-user](https://raw.githubusercontent.com/lfreneda/branch-feature-forking-workflow/master/images/24-delete-remote-origin-feature.png)

No final da limpeza teremos uma arvore parecida com a seguinte:

![graph-feature-merge](https://raw.githubusercontent.com/lfreneda/branch-feature-forking-workflow/master/images/25-graph-almost-done.png)

Note que o ponteiro da origin/master está desatualizado.
Na verdade, não usamos a __origin/master__ para nada. 
Podemos sincronizar sua master sob seu usuario :)

![master-user](https://raw.githubusercontent.com/lfreneda/branch-feature-forking-workflow/master/images/26-pushing-master-origin.png)

E finalmente, a arvore:

![graph-ufa](https://raw.githubusercontent.com/lfreneda/branch-feature-forking-workflow/master/images/27-graph-done.png)

TA-DA :tada:
