# Git Studies
Repositório para armazenar meu desenvolvimento no aprendizado de GIT.

Nesse texto utilizarei como base as aulas da playlist [Curso gratuito Git e Github pelo canal Tiago Matos](https://www.youtube.com/watch?v=2c7yWlpWDJM&list=PLcoYAcR89n-qbO7YAVj5S0alABLis_QVU&index=1) porém incrementarei o conteúdo com pesquisas a parte.

###### ⚠️ Atenção, os textos abaixo são resumos de cabeça do conteúdo, não representam ou substituem ver os vídeos ou fazer as pesquisas.

- [Vídeo-1: O que é GIT?](#video-1)
- [Vídeo-2: Commits](#video-2)
- [Vídeo-3: Instalação e configuração do GIT.](#video-2)
- [Vídeo-4: Criando Repositórios.](#video-4)
- [Vídeo-5: Colocando arquivos no stage](#video-5)
- [Vídeo-6: Fazendo Commits e Logs](#video-6)
- [Vídeo-7: Desfazendo commits:](#video-7)
- [Vídeo-8: Ignorando arquivos](#video-8)
- [Vídeo-9: Criando Branches e Gitflow](#video-9)
- [Vídeo-10: Fundindo Branches](#video-10)
- [Vídeo-11: Resolvendo conflitos](#video-11)
- [Vídeo-12: Iniciando com Github.](#video-12)
- [Vídeo-13: Simulando Múltiplos devs e pulls](#video-13)
- [Vídeo-14: Fazendo PR's](#video-14)
- [Vídeo-15: Fazendo Fork](#video-15)

Extra:
- [Conteúdos Git não abordados](#git-nao-abordado)
- [Conteúdos Github não abordados](#github-nao-abordado)

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

## Vídeo-2: Commits {#video-2}

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

## Vídeo-3: Instalação e configuração do GIT. {#video-3}

Nesse tópico irei apenas referenciar meu repositório de [configuração de ambiente de desenvolvimento](https://github.com/gabrieldeori/cfg_dev_environment/tree/main/first_config), no capítulo sobre GIT, observando apenas as diferenças na instalação do git no windows é feita através do exe.

## Vídeo-4: Criando Repositórios. {#video-4}

### Comandos básicos:
```sh
git init # Cria .git/inicia repositório
```

## Vídeo-5: Colocando arquivos no stage {#video-5}

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

## Vídeo-6: Fazendo Commits e Logs {#video-6}
### Comandos Commit:
```sh
git commit # Abre editor padrão para editar a mensagem de commit

git commit -m "mensagem" # Commita direto com a mensagem que está entre aspas.

git commit --m "mensagem" --author="pessoa <pessoa@mail.com>" # Modifica metadados do autor para o especificado
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

## Vídeo-7: Desfazendo commits: {#video-7}

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

## Vídeo-8: Ignorando arquivos {#video-8}
Para que o git ignore arquivos você pode simplesmente criar um arquivo de nome .gitignore e populá-lo com o que quiser:

```txt
.env
*.txt
teste.*
src
src/img
```

## Vídeo-9: Criando Branches e Gitflow {#video-9}
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

## Vídeo-10: Fundindo Branches {#video-10}
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

## Vídeo-11: Resolvendo conflitos {#video-11}

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

## Vídeo-12: Iniciando com Github. {#video-12}

Manter um repositório remoto é muito vantajoso, salva o progresso de desenvolvimento em um local mais seguro, já que sua máquina pode dar problema, facilita a visualização de outras pessoas do time, entre outras vantagens já discutidas.

### SSH
O vídeo cita como configurar o SSH, para não repetir, vou deixar o meu [configuração de ambiente de desenvolvimento](https://github.com/gabrieldeori/cfg_dev_environment/tree/main/first_config) que tem uma parte dedicada a como configurar o ssh.

### Importar código
Basta importar um código de outro repositório por um botão no frontend do github.

### Repositório Populado
Você pode criar um repositório no Github e adicionar um README nele e você terá seu repositório populado.

Após isso é só cloná-lo:
```sh
git clone git@github.com:organization/repository_name.git # Cria o clone com o nome do projeto

git clone git@github.com:organization/repository_name.git nome_diretorio # Cria o clone do projeto com o nome "nome_diretório"
```

### Sincronizando repositório existente:
Basta entrar no diretório do seu projeto e sincronizar da seguinte maneira:

```sh
git remote add origin git@github.com:organization/repository_name.git # Adiciona a um alias origin o link ssh especificado

git remote -v # Lista os alias definidos

git branch -M main

git push -u origin main
```

### Criando um repositório novo no PC
Basta criar no site do github um repositório vazio. (Sem README, Sem LICENÇA). E executar o fluxo abaixo:

```sh
echo "# repository_name" >> README.md

git init

git add README.md

git commit -m "first commit"

git branch -M main

git remote add origin git@github.com:organization/repository_name.git

git push -u origin main
```

### Mais sobre o push
```sh
git push origin main # Git envie para o alias "origin" o conteúdo da branch "main"

git push -u origin main # Cria um alias para a branch atual para enviar sempre de origin pra main

git push # Após o comando acima, irá fazer push de origin pra main direto
```

## Vídeo-13: Simulando Múltiplos devs e pulls {#video-13}
É um vídeo de exemplos, mas alguns comandos novos são:

```sh
git pull # Sincronizar as atualizações feitas em todas as branchs

git pull branch_especifica # Sincronizar branch específica
``` 

## Vídeo-14: Fazendo PR's {#video-14}
O pull-request no GitHub é uma forma de colaboração onde um colaborador pode sugerir mudanças no código de um repositório e iniciar uma discussão com os mantenedores. Ele permite que os mantenedores revisem e discutam as mudanças propostas antes de serem mescladas na branch principal do repositório.

É um processo mais visual no frontend do Github.

### Fique de olho
Sempre que for criar um pull-request, veja se a sua branch aponta para a branch que quer fazer merge, nem sempre é na main que queremos fazer merge.

Para isso existe um menu-dropdown em que é possível escolher para que branch estamos direcionando nosso PR.

Outro ponto é que também é possível fazer "merge", "squash" e "rebase" com o PR.

### Após o merge
Você pode usar a mesma branch de um pull request após mesclá-lo. Quando você mescla um pull request, as mudanças são aplicadas à branch de destino, mas a branch original ainda existe no repositório. Isso significa que você pode continuar a trabalhar nessa branch e fazer mais alterações se precisar.

Além disso, você também pode usar o histórico de um pull request após mesclá-lo. O GitHub mantém o registro de todos os pull requests que foram mesclados em uma determinada branch, permitindo que você acompanhe as mudanças e veja quem contribuiu para o código.

## Vídeo-15 Fazendo Fork {#video-15}
Fork é uma funcionalidade do GitHub que permite:

- Contribuir com projetos: Quando um usuário deseja contribuir com um projeto existente, ele pode criar um fork para fazer mudanças sem afetar o repositório original. Depois, pode enviar um pull request com as mudanças sugeridas para os mantenedores do repositório avaliarem.

- Criar projetos derivados: O fork também pode ser usado para criar um projeto derivado a partir de outro existente. Isso é útil quando o usuário deseja criar uma versão personalizada de um projeto existente ou usar o código como ponto de partida para um novo projeto.

- Armazenar uma cópia do repositório: O fork permite que um usuário tenha uma cópia completa de um repositório Git em seu próprio perfil do GitHub. Isso é útil para backup ou para acesso fácil a um repositório, mesmo que o repositório original seja excluído ou movido.

## Conteúdos Git não abordados {#git-nao-abordado}
### git stash
Permite salvar temporariamente as alterações em uma branch sem ter que fazer commit, o que pode ser útil quando você precisa mudar de branch rapidamente.

### git cherry-pick
Permite copiar um ou mais commits específicos de uma branch para outra.

### git bisect
Ajuda a identificar um commit específico que causou um problema, permitindo que você faça uma busca binária por um commit problemático.

### git submodules
Permite que você adicione um repositório dentro de outro repositório como um submódulo.

### git hooks
Permite que você execute scripts personalizados antes ou depois de determinados eventos do git, como um commit ou uma solicitação de pull.

### git reflog
Mantém um registro de todos os commits e alterações que ocorreram em uma branch, mesmo que eles tenham sido excluídos ou redefinidos.

### git rebase
Permite reorganizar a história de commits em uma branch, o que pode ser útil para manter uma branch limpa e organizada.

### git squash
Permite combinar vários commits em um único commit para tornar a história do git mais clara e organizada. Isso pode ser útil, por exemplo, para limpar uma branch antes de criar uma solicitação de pull, combinando vários commits em um único commit mais descritivo e fácil de entender. O comando git squash é usado em conjunto com o comando git rebase -i (interativo), que permite editar e reorganizar os commits em uma branch. Ao usar o git rebase -i, você pode marcar um ou mais commits para squash, o que criará um novo commit que combina as alterações desses commits em um único commit.

## Conteúdos Github não abordados {#github-nao-abordado}
### Issues

São usadas para relatar e rastrear bugs, solicitações de recursos e outras questões relacionadas a um projeto. Com as Issues, os usuários podem colaborar na resolução de problemas e discutir possíveis soluções. As issues são essenciais para um gerenciamento de projetos bem-sucedido e colaborativo.

### Actions
São usadas para criar workflows automatizados que são executados quando ocorrem eventos específicos em um repositório do GitHub. Por exemplo, quando uma nova solicitação de pull é aberta, um fluxo de trabalho pode ser acionado para testar as mudanças propostas e alertar os mantenedores do repositório sobre possíveis problemas.

### Projects
São usados para organizar e priorizar tarefas, Issues e pull requests em um repositório do GitHub. Com os Projects, os usuários podem criar quadros Kanban ou tabelas de rastreamento para ajudar a gerenciar o trabalho em andamento e visualizar o progresso do projeto.

### Wikis
Uma área wiki para documentação de um projeto, que pode ser editada por qualquer pessoa com acesso ao repositório.

### Gists
Uma maneira fácil de compartilhar pequenos trechos de código ou anotações com outras pessoas.

### Insights
Uma seção do GitHub que fornece informações sobre o uso e o desempenho de um repositório, incluindo informações sobre contribuidores, problemas, solicitações de pull e muito mais.

### Pages
Permite que um repositório do GitHub seja transformado em um site estático, tornando-o fácil de publicar e compartilhar.

### Security
Fornece informações sobre vulnerabilidades conhecidas e possíveis vulnerabilidades em um repositório do GitHub.

### Dependabot
Um serviço que verifica as dependências de um projeto e avisa quando há atualizações disponíveis, ajudando a manter o projeto atualizado e seguro.

### Codespaces
Permite criar um ambiente de desenvolvimento completo diretamente no navegador, facilitando a colaboração e a experimentação em projetos.