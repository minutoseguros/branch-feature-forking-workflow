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
