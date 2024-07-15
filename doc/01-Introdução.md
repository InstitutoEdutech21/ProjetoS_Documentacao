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
