![image](https://img.shields.io/badge/Netlify-00C7B7?style=for-the-badge&logo=netlify&logoColor=white)
![image](https://img.shields.io/badge/MongoDB-4EA94B?style=for-the-badge&logo=mongodb&logoColor=white)
![image](https://img.shields.io/badge/Angular-DD0031?style=for-the-badge&logo=angular&logoColor=white)
![image](https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white)
![image](https://img.shields.io/badge/Godot-478CBF?style=for-the-badge&logo=GodotEngine&logoColor=white)

# Introdução

O projeto consiste em uma plataforma educacional integrada composta por três componentes principais: um dashboard, um jogo e uma API que se conecta ao MongoDB. A plataforma foi desenvolvida para facilitar a gestão educacional, personalização de jogos educacionais e a monitorização do desempenho dos alunos.

## Componentes do Projeto

### 1. Dashboard

- Desenvolvido em Angular 18 utilizando componentes standalone.
- Funcionalidades:
  - Autenticação de usuários (professores, estudantes, administradores).
  - Cadastro e gerenciamento de professores, estudantes, salas de aula e escolas.
  - Personalização do jogo com criação e desbloqueio de fases.
  - Visualização de rankings, contato e FAQ.
  - Políticas de privacidade.

### 2. Jogo

- Desenvolvido em Godot usando GDScript.
- Interage com a API para autenticação e envio de dados de desempenho dos alunos.
- Funcionalidades:
  - Login de professores e alunos.
  - Professores podem desbloquear/bloquear fases e personalizar atividades.
  - Alunos jogam fases liberadas e têm seus stats enviados para a API.

### 3. API

- Conectada ao MongoDB para armazenamento e manipulação de dados.
- Funcionalidades de gerenciamento de escolas, professores, alunos e salas de aula.
- Roteamento detalhado para cada entidade com autenticação e autorização apropriadas.


# Get Started

Bem-vindo ao guia de início rápido do projeto! Este documento fornecerá as instruções necessárias para configurar e executar o projeto localmente.

## Requisitos

Antes de começar, certifique-se de ter os seguintes pré-requisitos instalados:

- [Node.js](https://nodejs.org/) (versão 14 ou superior)
- [Yarn](https://yarnpkg.com/) (gerenciador de pacotes)
- [Angular CLI](https://angular.io/cli) (versão 18 ou superior)
- [MongoDB](https://www.mongodb.com/) (banco de dados)
- [Godot Engine](https://godotengine.org/) (para desenvolvimento do jogo)
- [Git](https://git-scm.com/) (para controle de versão)

## Passos para Configuração

### 1. Clone o Repositório

Primeiro, clone o repositório do projeto para sua máquina local:
Obs.: O repo é privado, solicite acesso com o Instituto Edutech para realizar o clone

```bash
git clone https://github.com/holyicecream/Jogo-Web-2-Edutech21.git
cd Jogo-Web-2-Edutech21
```


Após isso, você deve instalar as dependências do projeto utilizando Yarn
```bash
yarn install
```

Para inicializar o dashboard localmente, utilize `ng serve`
```bash
ng serve
```

### API

Para acessar a api, faça clone do repo:
```bash
git clone https://github.com/InstitutoEdutech21/programaS-api.git
cd programaS-api
```

Após isso, você deve instalar as dependências do projeto utilizando Yarn
```bash
yarn install
```

Para inicializar o a API localmente, utilize `yarn dev`
```bash
yarn dev
```

### JOGO
Primeiro, clone o repositório do projeto para sua máquina local:
Obs.: O repo é privado, solicite acesso com o Instituto Edutech para realizar o clone

```bash
git clone https://github.com/InstitutoEdutech21/Biodefensores.git
cd Biodefensores
git checkout correcoes-v2
```

Após isso abra o GODOT e adicione a pasta do reposítório ao GODOT.

Veja os outros arquivos da pasta `\doc` para mais detalhes.