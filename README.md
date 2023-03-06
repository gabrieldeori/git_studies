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
