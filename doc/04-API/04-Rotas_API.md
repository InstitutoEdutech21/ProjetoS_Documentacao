# Rotas da API

Este documento fornece uma descrição detalhada das principais rotas da API do projeto, incluindo uma introdução ao que são rotas de API e como elas funcionam no contexto de uma aplicação web.

## Conceitos Básicos

### Rota de API

Uma rota de API é um endpoint (ponto de acesso) exposto por um servidor web que permite a interação com os dados e funcionalidades do sistema. Cada rota corresponde a uma URL específica e um método HTTP (GET, POST, PUT, DELETE, etc.), permitindo que diferentes operações sejam realizadas, como criar, ler, atualizar ou deletar dados.

### Método HTTP

Os métodos HTTP definem a ação a ser realizada em uma rota de API. Os mais comuns são:
- **GET:** Recupera dados do servidor.
- **POST:** Envia dados para serem processados no servidor.
- **PUT:** Atualiza dados existentes no servidor.
- **DELETE:** Remove dados do servidor.

## Principais Rotas de API

### `/api/school`

- **Rota:** `school_route`
- **Descrição:** Gerencia todas as operações relacionadas às escolas, como criação, atualização, obtenção e remoção de escolas do banco de dados.

### `/api/teacher`

- **Rota:** `teacher_route`
- **Descrição:** Gerencia todas as operações relacionadas aos professores, incluindo criação, atualização, obtenção e remoção de dados de professores.

### `/api/classroom`

- **Rota:** `classroom_route`
- **Descrição:** Gerencia operações relacionadas às salas de aula, permitindo a criação, atualização, obtenção e remoção de salas.

### `/api/student`

- **Rota:** `student_route`
- **Descrição:** Gerencia operações relacionadas aos alunos, incluindo criação, atualização, obtenção e remoção de dados de alunos.

### `/api/score`

- **Rota:** `score_route`
- **Descrição:** Gerencia as pontuações dos alunos, permitindo a obtenção e manipulação dos dados de desempenho dos alunos.

### `/api/admin`

- **Rota:** `adm_route`
- **Descrição:** Gerencia operações administrativas, como login de administradores e manipulação de dados de administradores.

### `/api/logout`

- **Rota:** `logout_route`
- **Descrição:** Gerencia a operação de logout, permitindo que os usuários terminem suas sessões no sistema.

### `/api/docs`

- **Rota:** `doc_router`
- **Descrição:** Fornece a documentação da API, detalhando todas as rotas disponíveis e como usá-las.

### `/api/cityAverage`

- **Rota:** `cityAverage_route`
- **Descrição:** Gerencia a obtenção de médias de desempenho por cidade, permitindo análises comparativas entre diferentes localidades.

### `/api/accessLevel`

- **Rota:** `accessLevel_route`
- **Descrição:** Gerencia os níveis de acesso dos usuários, definindo permissões e restrições de acordo com suas funções no sistema.

### `/api/email`

- **Rota:** `email_route`
- **Descrição:** Gerencia o envio de emails, permitindo comunicação automatizada ou manual com os usuários.

### `/api/tester`

- **Rota:** `test_route`
- **Descrição:** Rota destinada para testes de funcionalidades da API.

### `/api/token`

- **Rota:** `token_route`
- **Descrição:** Gerencia operações relacionadas a tokens de acesso, como verificação e geração de tokens, além de testes de conexão.

## Detalhes das Rotas

### `adm_route`

- **`POST /admin/login`**: Realiza o login do administrador.
  - **Handler:** `LoginADM`
  - **Descrição:** Verifica as credenciais do administrador e retorna um token de autenticação se as credenciais forem válidas.

- **`PUT /admin`**: Atualiza os dados do administrador.
  - **Handlers:** `Login`, `UpdateADM`
  - **Descrição:** Permite que o administrador, após estar autenticado, atualize suas informações no sistema.

- **`GET /admin`**: Obtém dados do administrador.
  - **Handlers:** `Login`, `GetAdminDatas`
  - **Descrição:** Retorna as informações do administrador autenticado.

### `student_route`

- **`POST /aluno`**: Cria um novo aluno no banco de dados.
  - **Handlers:** `Login`, `createStudentInDatabase`
  - **Descrição:** Permite que um administrador ou professor adicione um novo aluno ao sistema.

- **`DELETE /aluno/:id`**: Deleta um aluno do banco de dados.
  - **Handlers:** `Login`, `deleteStudentFromDatabase`
  - **Descrição:** Remove um aluno específico, identificado pelo seu ID, do sistema.

- **`PUT /aluno`**: Atualiza os dados de um aluno.
  - **Handlers:** `Login`, `updateStudentFromDatabase`
  - **Descrição:** Permite que os dados de um aluno existente sejam atualizados.

- **`POST /aluno/login`**: Realiza o login de um aluno.
  - **Handler:** `LoginStudent`
  - **Descrição:** Verifica as credenciais do aluno e retorna um token de autenticação se as credenciais forem válidas.

- **`GET /aluno`**: Obtém dados de todos os alunos.
  - **Handler:** `getStudentFromDatabase`
  - **Descrição:** Retorna uma lista de todos os alunos registrados no sistema.

- **`GET /aluno/school`**: Obtém dados dos alunos de uma escola específica.
  - **Handler:** `getStudentFromSchool`
  - **Descrição:** Retorna informações dos alunos associados a uma escola específica.

- **`GET /aluno/:id`**: Obtém dados de um aluno específico.
  - **Handler:** `getStudentByIdFromDatabase`
  - **Descrição:** Retorna as informações de um aluno identificado pelo seu ID.

- **`PUT /aluno/mundos`**: Atualiza o progresso de mundos de um aluno.
  - **Handlers:** `Login`, `updateStudentWorldFromDatabase`
  - **Descrição:** Permite atualizar os mundos que um aluno completou ou está jogando.

- **`PUT /aluno/fases`**: Atualiza o progresso de fases de um aluno.
  - **Handlers:** `Login`, `updateStudentLevelFromDatabase`
  - **Descrição:** Permite atualizar as fases que um aluno completou ou está jogando.

- **`POST /aluno/acerto`**: Registra um acerto de um aluno.
  - **Handlers:** `Login`, `addStudentRightInDatabase`
  - **Descrição:** Adiciona um registro de resposta correta de um aluno no sistema.

- **`POST /aluno/erro`**: Registra um erro de um aluno.
  - **Handlers:** `Login`, `addStudentErrorInDatabase`
  - **Descrição:** Adiciona um registro de resposta incorreta de um aluno no sistema.

- **`POST /aluno/coins`**: Adiciona moedas a um aluno.
  - **Handlers:** `Login`, `addStudentCoins`
  - **Descrição:** Atualiza o saldo de moedas de um aluno.

- **`GET /media/aluno`**: Obtém a média de desempenho de todos os alunos.
  - **Handler:** `getAllStudentsAverages`
  - **Descrição:** Retorna as médias de desempenho de todos os alunos registrados no sistema.

- **`POST /aluno/level-performance`**: Adiciona o desempenho de um aluno em um nível.
  - **Handler:** `addLevelPerformanceToDatabase`
  - **Descrição:** Registra o desempenho de um aluno em um nível específico do jogo.

- **`GET /aluno/primeira-tentativa/:studentId`**: Obtém a primeira tentativa de um aluno em um nível.
  - **Handler:** `getFirstStudentPlayByStudentId`
  - **Descrição:** Retorna os dados da primeira tentativa de um aluno em um nível específico, identificado pelo ID do aluno.

- **`GET /aluno/melhor-tentativa/:studentId`**: Obtém a melhor tentativa de um aluno em um nível.
  - **Handler:** `getBestStudentPlayByStudentId`
  - **Descrição:** Retorna os dados da melhor tentativa de um aluno em um nível específico, identificado pelo ID do aluno.

### `school_route`

- **`POST /escola`**: Cria uma nova escola no banco de dados.
  - **Handler:** `createSchoolInDatabase`
  - **Descrição:** Permite a adição de uma nova escola ao sistema.

- **`PUT /escola`**: Atualiza os dados de uma escola.
  - **Handlers:** `Login`, `updateSchoolFromDatabase`
  - **Descrição:** Permite que os dados de uma escola existente sejam atualizados.

- **`GET /escola`**: Obtém dados de todas as escolas.
  - **Handler:** `getSchoolFromDatabase`
  - **Descrição:** Retorna uma lista de todas as escolas registradas no sistema.

- **`GET /escola/:id`**: Obtém dados de uma escola específica.
  - **Handlers:** `Login`, `getSchoolByIdFromDatabase`
  - **Descrição:** Retorna as informações de uma escola identificada pelo seu ID.

- **`DELETE /escola/:id`**: Deleta uma escola do banco de dados.
  - **Handlers:** `Login`, `deleteSchoolFromDatabase`
  - **Descrição:** Remove uma escola específica, identificada pelo seu ID, do sistema.

- **`POST /escola/login`**: Realiza o login de uma escola.
  - **Handler:** `LoginSchool`
  - **Descrição:** Verifica as credenciais de login de uma escola e retorna um token de autenticação se as credenciais forem válidas.

- **`GET /media/escola`**: Obtém a média de desempenho das escolas.
  - **Handlers:** `Login`, `getSchoolAverage`
  - **Descrição:** Retorna a média de desempenho de todas as escolas registradas no sistema.

- **`POST /escola/niu`**: Verifica o número único de identificação (NIU) de uma escola.
  - **Handler:** `CheckNIU`
  - **Descrição:** Verifica se um NIU específico está associado a alguma escola registrada no sistema.

### `logout_route`

- **`GET /logout`**: Realiza o logout do usuário.
  - **Handler:** `Logout`
  - **Descrição:** Finaliza a sessão do usuário no sistema, invalidando o token de autenticação.

### `teacher_route`

- **`POST /professor`**: Cria um novo professor no banco de dados.
  - **Handler:** `createTeacherInDatabase`
  - **Descrição:** Permite a adição de um novo professor ao sistema.

- **`DELETE /professor/:id`**: Deleta um professor do banco de dados.
  - **Handlers:** `Login`, `deleteTeacherFromDatabase`
  - **Descrição:** Remove um professor específico, identificado pelo seu ID, do sistema.

- **`PUT /professor`**: Atualiza os dados de um professor.
  - **Handlers:** `Login`, `updateTeacherFromDatabase`
  - **Descrição:** Permite que os dados de um professor existente sejam atualizados.

- **`POST /professor/login`**: Realiza o login de um professor.
  - **Handler:** `LoginTeacher`
  - **Descrição:** Verifica as credenciais de login de um professor e retorna um token de autenticação se as credenciais forem válidas.

- **`GET /professor`**: Obtém dados de todos os professores.
  - **Handler:** `getTeacherFromDatabase`
  - **Descrição:** Retorna uma lista de todos os professores registrados no sistema.

- **`GET /professor/:id`**: Obtém dados de um professor específico.
  - **Handlers:** `Login`, `getTeacherByIdFromDatabase`
  - **Descrição:** Retorna as informações de um professor identificado pelo seu ID.

### `classroom_route`

- **`POST /sala`**: Cria uma nova sala de aula no banco de dados.
  - **Handler:** `createClassroomInDatabase`
  - **Descrição:** Permite a adição de uma nova sala de aula ao sistema.

- **`POST /sala/teacher`**: Obtém salas de aula de um professor específico.
  - **Handler:** `getClassroomByTeacherFromDatabase`
  - **Descrição:** Retorna as salas de aula associadas a um professor específico.

- **`DELETE /sala/:id`**: Deleta uma sala de aula do banco de dados.
  - **Handlers:** `Login`, `deleteClassroomFromDatabase`
  - **Descrição:** Remove uma sala de aula específica, identificada pelo seu ID, do sistema.

- **`PUT /sala`**: Atualiza os dados de uma sala de aula.
  - **Handlers:** `Login`, `updateClassroomFromDatabase`
  - **Descrição:** Permite que os dados de uma sala de aula existente sejam atualizados.

- **`GET /sala`**: Obtém dados de todas as salas de aula.
  - **Handler:** `getClassroomFromDatabase`
  - **Descrição:** Retorna uma lista de todas as salas de aula registradas no sistema.

- **`GET /sala/:id`**: Obtém dados de uma sala de aula específica.
  - **Handlers:** `Login`, `getClassroomByIdFromDatabase`
  - **Descrição:** Retorna as informações de uma sala de aula identificada pelo seu ID.

- **`GET /sala/escola/:id`**: Obtém salas de aula de uma escola específica.
  - **Handlers:** `Login`, `getClassroomBySchoolFromDatabase`
  - **Descrição:** Retorna as salas de aula associadas a uma escola específica, identificada pelo seu ID.

- **`GET /media/sala`**: Obtém a média de desempenho das salas de aula.
  - **Handlers:** `Login`, `getClassroomAverages`
  - **Descrição:** Retorna a média de desempenho de todas as salas de aula registradas no sistema.

- **`POST /sala/levels`**: Obtém os níveis de uma sala de aula.
  - **Handlers:** `Login`, `getLevels`
  - **Descrição:** Retorna os níveis de atividade configurados para uma sala de aula específica.

- **`POST /sala/set-levels`**: Configura os níveis de uma sala de aula.
  - **Handlers:** `Login`, `setLevels`
  - **Descrição:** Permite configurar os níveis de atividade para uma sala de aula específica.

- **`POST /sala/names`**: Obtém o nome de uma sala de aula.
  - **Handler:** `getClassroomName`
  - **Descrição:** Retorna o nome de uma sala de aula específica.

- **`POST /sala/customLevels`**: Personaliza os níveis de uma sala de aula.
  - **Handler:** `customizeClassLevels`
  - **Descrição:** Permite a personalização dos níveis de atividade para uma sala de aula específica.

- **`GET /sala/customLevels/:id`**: Obtém os níveis personalizados de uma sala de aula.
  - **Handler:** `getCustomClassLevels`
  - **Descrição:** Retorna os níveis de atividade personalizados para uma sala de aula específica.

### `email_route`

- **`POST /sendEmail`**: Envia um email.
  - **Handler:** `sendEmail`
  - **Descrição:** Permite o envio de emails para os usuários do sistema.

### `token_route`

- **`POST /check-token`**: Verifica a validade de um token.
  - **Handler:** `CheckToken`
  - **Descrição:** Verifica se um token de autenticação é válido e pode ser usado para acessar recursos protegidos.

- **`GET /gen-token`**: Gera um novo token de autenticação.
  - **Handler:** `GenToken`
  - **Descrição:** Gera um novo token de autenticação para um usuário.

- **`GET /cloudflare`**: Testa a integração com Cloudflare.
  - **Handler:** `TestCloudflare`
  - **Descrição:** Realiza um teste de conexão com a plataforma Cloudflare para verificar a disponibilidade e integridade da conexão.


