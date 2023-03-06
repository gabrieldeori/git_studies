# Git Studies
Repositório para armazenar meu desenvolvimento no aprendizado de GIT.

Nesse texto utilizarei como base as aulas da playlist [Curso gratuito Git e Github pelo canal Tiago Matos](https://www.youtube.com/watch?v=2c7yWlpWDJM&list=PLcoYAcR89n-qbO7YAVj5S0alABLis_QVU&index=1) porém incrementarei o conteúdo com pesquisas a parte.

###### ⚠️ Atenção, os textos abaixo são resumos de cabeça do conteúdo, não representam ou substituem ver os vídeos ou fazer as pesquisas.

## Vídeo-1: O que é GIT?

Git é um software para rastrear alterações em qualquer conjunto de arquivos, geralmente usado para coordenar o trabalho entre programadores que desenvolvem código-fonte de forma colaborativa durante o desenvolvimento de software. Seus objetivos incluem:
Velocidade
Integridade de dados
Suporte a fluxo de trabalho não lineares distribuídos

"Suporte a fluxo de trabalho não lineares distribuídos" se refere à capacidade do Git de lidar com colaboração distribuída e fluxos de trabalho complexos que podem ter múltiplas ramificações (branches) e pontos de origem (origins). Isso permite que várias pessoas trabalhem em diferentes partes do mesmo projeto simultaneamente, com cada pessoa contribuindo para o desenvolvimento do projeto em sua própria ramificação e, em seguida, mesclando (merge) suas alterações com outras ramificações

### O que é possível com o GIT
Salvar múltiplas versões do projeto em um único diretório
Trocar essas versões com comandos simples
Trabalhar simultaneamente em 2 ou mais funcionalidades distintas sem que uma atrapalhe a outra
Colaborar com outros programadores nos mesmos arquivos

### O que é GitHub?

GitHub, Inc. é um provedor de hospedagem na internet para desenvolvimento de software e controle de versão usando Git. Ele oferece o controle de versão distribuída e a funcionalidade de gerenciamento de código-fonte do Git, além de seus próprios recursos.


#### Extra
Hoje em dia podemos argumentar que o GitHub vai além disso, servindo como rede social e portfólio para desenvolvedores, vitrine para projetos open-source, compartilhamento fácil de projetos, facilita muito na colaboração em projetos na comunidade open-source.

Traz ferramentas interessantes ao desenvolvimento em equipe que facilitam a interação com o git como a possibilidade por exemplo de configurar merge com aprovações de code-reviews.

Possui ferramentas administrativas básicas como fazer Assignees, separar por Labels, Projects, Milestones. Também é possível criar “Organizações” e dividir melhor as responsabilidades.

O Github actions traz a possibilidade de criar um fluxo de trabalho, por exemplo para automatizar deploys ou configurar um fluxo de merge liberando-o após checagem do lint e/ou após a aferição de todos os testes unitários e/ou code-review.

Por fim o Github também traz a funcionalidade do Github Copilot que é uma inteligência artificial de assistência de código, que tem como objetivo, auxiliar desenvolvedores com códigos gerados baseados em códigos de diversos repositórios de sua base.

## Vídeo-2: 

### Repositório
Essencialmente git repository é um diretório chamado de .git dentro do seu projeto. Este repositório rastreia todas as mudanças feitas nos arquivos do seu projeto, construindo um histórico ao longo do tempo.

### Commit
É enviar e guardar uma operação ou alteração, e, no Git é salvar uma nova versão de um conjunto de arquivos em um repositório, em outras palavras pode ser interpretado como um marco histórico. Uma boa prática é fazer commits em momentos importantes de alteração do código, criação de uma feature ou correção de um bug por exemplo.

#### Estágios de commit
- Modified
O git percebe uma diferença entre o arquivo do último commit e registra esse arquivo como modificado. É possível configurar para que algum arquivo ou tipo de arquivo não seja visto pelo git, então ele não será mais observado. Comandos:
  - git pull
  - git status
  - Configurar .gitignore para o git não observar algo.

- Staging
O programador decide que dentre todos os arquivos, aquele ou aqueles arquivos devem ter suas diferenças(patches) salvas em um local temporário, em um local que fique visível para ser commitado posteriormente. Comandos:
  - git status
  - git add arquivos

- Commited
O programador então decide que é a hora de algumas diferenças(patches) virarem um “marco histórico” e serem adicionadas ao histórico do repositório. Comandos:
  - git status
  - git commit -m “feat: pagamento com cartão de crédito”
  - git log
  - git push destino branch


### Branch
É uma linha de desenvolvimento independente criada a partir de um commit específico que permite programadores a trabalharem em diferentes partes do mesmo projeto, fazendo commits de forma independente e simultaneamente sem afetar outras branchs nem a linha de desenvolvimento de origem dessa branch.

#### Comandos básicos
```sh
git branch # Mostra as branchs atuais
```

## Vídeo-3: Instalação e configuração do GIT.

Nesse tópico irei apenas referenciar meu repositório de [configuração de ambiente de desenvolvimento](https://github.com/gabrieldeori/cfg_dev_environment/tree/main/first_config), no capítulo sobre GIT, observando apenas as diferenças na instalação do git no windows é feita através do exe.

## Vídeo-4: Criando Repositórios.

### Comandos básicos:
```sh
git init # Cria .git/inicia repositório
```

## Vídeo-5: Colocando arquivos no stage

###### ⚠️ Atençaõ: Deve-se entender o contexto do diretório onde os comandos estão sendo executados. Por exemplo se seu repositório for em projeto1 e o seu terminal estiver em projeto1/src, os comandos serão executados dentro do contexto da pasta src, ou seja observando os arquivos e diretórios de src.

### Comandos para observar:
```sh
git status # Mostra o log de stage, ou o que está em stage

git status --short # Mostra uma versão menor do log de stage

# Existem várias options diferentes pra alterar a saída
```

### Comandos para adicionar:
```sh
git add index.html # Adiciona arquivo index.html

git add *.html # Adiciona qualquer arquivo extensão .html

git add index* # Adiciona qualquer arquivo que comece com index

git add src # Adiciona o diretório src (a partir de onde executou-se o comando)

git add src/dark-theme # Adiciona o diretório dark-theme que está dentro de src

git add . # Adiciona todos os arquivos e diretórios
```

### Comandos para remover:
```sh
git restore --staged . # Retira todos os diretórios e arquivos da área de stage

git rm --cached index.html # Retira apenas o arquivo index.html
```

## Vídeo-6: Fazendo Commits e Logs
### Comandos Commit:
```sh
git commit # Abre editor padrão para editar a mensagem de commit

git commit -m "mensagem" # Commita direto com a mensagem que está entre aspas.
```

###### ⚠️Importante lembrar que o histórico mostrado usa o contexto da branch em que está.

###
```sh
git log # Mostra o log de históricos de commits do repositório

git log --oneline # Forma condensada, apenas as mensagens de commit

git log --graph # Exibe o histórico de commits graficamente

git log --decorate # Exibe informações adicionais ao lado dos commits.

git log --graph --decorate --oneline # Tente essa
```

## Vídeo-7: Desfazendo commits:

### 🚨 Muito cuidado! Esses comandos são muito poderosos e podem quebrar um repositório as vezes de forma não reversível. Com grandes poderes vem grandes responsabilidades.

###  🟢 Checkout 🟢
Esse é um comando mais seguro, já que ele não faz alterações no histórico de commits. Caso faça algum commit uma nova branch será criada e a original entrará em modo de "detenção"

Aqui seria como viajar no tempo apenas como observador, mas se modificar algo no passado, você criará uma nova linha do tempo.

#### Fluxo de uso
```sh
git log # Pegue o hash do commit desejado, não precisa ser ele completo, normalmente 5 ou 6 caracteres são suficientes

git checkout h4shcomm1t # o HEAD será apontado para o commit do hash específico.
```

### 🟡 Revert 🟡
Esse é um comando que deve ser usado com muita atenção, mesmo ele não alterando o histórico de commits, ele irá criar um novo commit trazendo de volta alterações do passado o que pode causar alguns conflitos.

Imagine que quer reformar uma casa antiga destruída usando informação do passado, você não copia a casa e traz ela por inteiro, você copiaria uma lista de todas as diferenças que a casa atual tem da anterior os danos que a casa sofreu e com essa informação reverteria cada ítem da lista para o estado mais antigo.

```sh
git log # Pegue o hash do commit desejado

git revert h4shcomm1t # Reverterá para o ponto em específico
```

### 🔴 Reset 🔴
Esse comando deve ser usado apenas em situações que ele realmente é necessário, aqui você tem que ter certeza que não quer mais nenhum commit que foi feito naquela branch, o reset irá apagar os commits.

É como se viajasse do futuro ao passado e apagasse toda a linha do tempo entre essa viagem.

```sh
git reset h4shcomm1t # Volta ao commit especificado, porém mantém alterações atuais não commitadas

git reset --hard h4shcomm1t # Volta ao commit especificado descartando alterações não commitadas
```

## Vídeo-8: Ignorando arquivos
Para que o git ignore arquivos você pode simplesmente criar um arquivo de nome .gitignore e populá-lo com o que quiser:

```txt
.env
*.txt
teste.*
src
src/img
```

## Vídeo-9: Criando Branches e Gitflow
Ao iniciar o projeto uma branch principal chamada main(master nas versões antigas) é criada. Porém você pode criar suas branchs também utilizando:

```sh
git branch # Lista branchs | * ou colorido é a branch que está

git branch nome_branch # Cria uma branch nova

git checkout nome_branch # Faz o checkout para a branch com o valor inserido

git checkout -b nome_branch # Cria uma branch e faz o checkout apenas com 1 comando.

git branch -d nome_branch # Deleta a branch mas impede a deleção caso haja commits não incorporados a outra branch

git branch -D nome_branch # Força deleção da branch mesmo que os commits dessa branch não tenham sido incorporados em outra branch ou não exista referências a esses commits em outra branch
```

### Gitflow
É sempre bom desenvolver features em branchs derivadas da principal, e existem algumas metodologias para separar as diversas etapas de desenvolvimento.

Uma dessas metodologias é o Gitflow, que separa em 4 branchs principais:

- main: Ambiente de produção, versão estável do código
- deploy: Temporária para implantação em ambiente de produção
- test: Para validar alterações antes do deploy.
- development: Para desenvolvimento de novas funcionalidades

No caso um programador por exemplo, desenvolveria uma feature em uma branch derivada da branch development.

Mas fique atento, nem todas as operações utilizam essa metodologia, ou talvez use com alguma variação.

## Vídeo-10: Fundindo Branches
```sh
git checkout branch_destinataria # Indo para a branch_destinataria, a que receberá as alterações

git merge branch_remetente # Trazendo para a branch_destinatária as modificações feitas na branch_remetente
```

No caso do exemplo entramos na branch_destinatária e puxamos as alterações que foram feitas na branch_remetente.

"git incorpore na branch que estou as alterações da branch de nome nome_branch"

```sh
git log # Se fizer um git log perceberá que os commits serão preservados ao realizar o merge
```

### Apenas por curiosidade

Existem outras estratégias de merge, como o squash e o rebase, mas deixaremos pra outro momento.

No vídeo é mencionado estratégias de merge automáticas, entre elas destaca-se:

#### Estratégia de merge automática "Fast-forward":

Tipo de merge no Git que ocorre quando não há conflitos entre duas branches que estão sendo mescladas. Nesse caso, o Git simplesmente avança a branch atual até a ponta da branch a ser mesclada, incorporando todas as alterações dessa branch sem criar um novo commit de merge.

#### Estratégia de merge automática "Recursiva":

Forma de realizar um merge no Git que é usada quando há conflitos entre as branches que estão sendo mescladas. Nesse caso, o Git cria um novo commit de merge que combina as alterações de ambas as branches e resolve quaisquer conflitos encontrados. Esse processo é chamado de "merge recursivo" porque o Git pode precisar mesclar commits de merge anteriores para resolver todos os conflitos.

## Vídeo-11: Resolvendo conflitos

As vezes o git não consegue resolver sozinho os conflitos do código e para isso é necessária uma intervenção manual do desenvolvedor.

Existem duas versões e o desenvolvedor deverá escolher entre uma ou outra versão. O mais importante é comunicar com o time e decidir em conjunto as prioridades e como resolver os conflitos. As vezes é possível que ocorra conflito de código em linhas, mas não na lógica do código o que permite manter as duas versões.

Conflito de lógica:
```css
22 body: {
<<<<<< HEAD
23  color: red;
======
23 color: blue;
>>>>>> branch_remetente
}
```
É necessário decidir qual a versão.

Conflito de linha
```css
22 body: {
<<<<<< HEAD
23 background-color: red;
======
23 color: blue;
>>>>>> branch_remetente
}
```
É possível manter as duas versões.

Pra resolver basta apagar os wrappers que o git criou e o código que não for utilizar e salvar, depois é só fazer um git-commit. Ex:

```css
22 body: {
<<<<<< HEAD
23  color: red;
======
23 color: blue;
>>>>>> branch_remetente
}
```
Fica:
```css
22 body: {
23  color: red;
}
```
Faz:

```sh
git commit # Gerará a mensagem padrão do git. Basta salvar e fechar o editor.
```

Dependendo do editor ou ide que você estiver usando é possível resolver conflitos em uma ferramenta.
