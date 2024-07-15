# Rotas do Dashboard

Este documento descreve detalhadamente a estrutura das rotas do dashboard do projeto, incluindo uma introdução sobre os conceitos básicos de componentes, guards e rotas no Angular, para que qualquer pessoa, mesmo sem conhecimento prévio de Angular, possa entender cada rota e seu propósito.

## Conceitos Básicos

### Componente

Um componente é um bloco de construção da interface do usuário em uma aplicação Angular. Cada componente controla uma parte específica da tela, chamada de "view". Um componente geralmente consiste de três partes principais:
- **HTML Template:** Define a estrutura e o layout da view.
- **CSS Styles:** Define o estilo visual da view.
- **TypeScript Class:** Define a lógica e o comportamento do componente.

### Rota

Uma rota define um caminho na URL que corresponde a um componente específico. Quando um usuário navega para uma URL específica, o Angular exibe o componente correspondente àquela rota. As rotas ajudam a organizar a navegação dentro da aplicação.

### Guard

Um guard é uma função que o Angular executa antes de permitir a navegação para uma rota específica. Os guards podem ser usados para proteger rotas, verificando se um usuário tem permissões adequadas ou se está autenticado antes de permitir o acesso à rota.

## Estrutura das Rotas

### Rotas Principais

#### `/login`
- **Componente:** `LoginComponent`
- **Descrição:** Esta rota leva o usuário à página de login. Aqui, o usuário insere suas credenciais (nome de usuário e senha) para acessar o sistema. É a primeira etapa para garantir que apenas usuários autorizados possam utilizar a aplicação.

#### `/dashboard`
- **Componente:** `DashboardComponent`
- **Descrição:** Esta é a rota principal do dashboard, que serve como a página inicial após o login. O dashboard é uma interface que agrega várias funcionalidades e subseções, permitindo ao usuário acessar diferentes partes do sistema.
- **Guarda:** `authTokenGuard`
  - **Descrição:** Este guard verifica se o usuário está autenticado (logado) antes de permitir o acesso ao dashboard. Se o usuário não estiver autenticado, ele será redirecionado para a página de login.

#### `/politica-privacidade`
- **Componente:** `PoliticasPrivacidadeComponent`
- **Descrição:** Esta rota leva o usuário à página que detalha a política de privacidade da aplicação. Aqui, os usuários podem ler sobre como suas informações pessoais são coletadas, usadas e protegidas pela aplicação.

#### `**`
- **Redirecionamento:** `/dashboard`
- **Descrição:** Esta rota curinga redireciona qualquer URL não reconhecida para o dashboard. Isso ajuda a evitar erros e garantir que o usuário sempre seja levado a uma página válida.

### Rotas Filhas do Dashboard

As rotas filhas estão disponíveis apenas após o usuário estar autenticado e ter acessado o dashboard. Elas representam diferentes seções e funcionalidades específicas dentro do dashboard.

#### `/dashboard/home`
- **Componente:** `DefaultDashboardComponent`
- **Descrição:** Esta é a página inicial do dashboard. Aqui, o usuário vê uma visão geral do sistema, com informações importantes ou um resumo das atividades recentes.

#### `/dashboard/professor`
- **Componente:** `ProfessorComponent`
- **Descrição:** Permite a gestão de professores. Nesta página, os administradores ou usuários autorizados podem adicionar novos professores, editar informações existentes ou remover professores do sistema.
- **Guarda:** `authSchoolGuard`
  - **Descrição:** Este guard assegura que apenas usuários com permissões específicas relacionadas à gestão escolar podem acessar esta rota.

#### `/dashboard/estudante`
- **Componente:** `StudentComponent`
- **Descrição:** Permite a gestão de estudantes. Aqui, os usuários podem cadastrar novos alunos, editar informações de alunos existentes ou remover alunos do sistema.

#### `/dashboard/salas`
- **Componente:** `CriarSalaComponent`
- **Descrição:** Permite a criação e gestão de salas de aula. Nesta seção, os usuários podem definir novas salas, editar as existentes ou excluí-las conforme necessário.

#### `/dashboard/escolas`
- **Componente:** `CriarSalaComponent`
- **Descrição:** Permite a criação e gestão de escolas. Os administradores podem adicionar novas escolas ao sistema, atualizar informações ou remover escolas.
- **Guarda:** `authAdminGuard`
  - **Descrição:** Este guard assegura que apenas administradores (usuários com nível de acesso mais alto) podem acessar esta rota.

#### Rotas de Personalização de Jogo

Estas rotas permitem a personalização de diferentes aspectos do jogo, acessíveis apenas por professores.

- **`/dashboard/personalizar/fases`**
  - **Componente:** `PersonalizarFasesComponent`
  - **Descrição:** Permite aos professores personalizar as fases do jogo. Nesta página, os professores podem definir quais fases estarão disponíveis, ajustar dificuldades e configurar detalhes específicos das fases.
  - **Guarda:** `authTeacherGuard`
    - **Descrição:** Este guard assegura que apenas usuários com permissões de professor podem acessar esta rota.

- **`/dashboard/personalizar/atividade-personalizada`**
  - **Componente:** `CustomPlataformsComponent`
  - **Descrição:** Permite aos professores personalizar atividades específicas dentro do jogo. Professores podem criar ou modificar atividades que os alunos encontrarão no jogo, adaptando-as para melhor atender às necessidades educacionais.
  - **Guarda:** `authTeacherGuard`
    - **Descrição:** Este guard assegura que apenas usuários com permissões de professor podem acessar esta rota.

- **`/dashboard/personalizar/desbloquear-fases`**
  - **Componente:** `UnlockLevelsComponent`
  - **Descrição:** Permite aos professores desbloquear fases específicas para os alunos. Professores podem decidir quais fases do jogo estarão acessíveis para os alunos, controlando o progresso e o acesso ao conteúdo.
  - **Guarda:** `authTeacherGuard`
    - **Descrição:** Este guard assegura que apenas usuários com permissões de professor podem acessar esta rota.

#### `/dashboard/contato`
- **Componente:** `ContactComponent`
- **Descrição:** Página de contato onde os usuários podem enviar mensagens ou obter informações de contato. É um canal direto para comunicação com os administradores ou suporte da aplicação.

#### `/dashboard/ranking`
- **Componente:** `RankingComponent`
- **Descrição:** Exibe a classificação ou ranking dos alunos com base em suas performances no jogo. Os usuários podem ver como os alunos se comparam uns com os outros em termos de desempenho.

#### `/dashboard/faq`
- **Componente:** `FaqComponent`
- **Descrição:** Página de Perguntas Frequentes (FAQ), fornecendo respostas para dúvidas comuns dos usuários. Esta seção ajuda a resolver problemas comuns e oferece orientação sobre o uso da aplicação.

## Conclusão

Este documento fornece uma visão detalhada das rotas do dashboard, explicando cada rota e seu propósito de maneira acessível para qualquer pessoa, independentemente do seu conhecimento técnico. Com estas informações, espera-se que os usuários possam navegar e utilizar o dashboard de forma eficaz.
