# Detalhes do Jogo

## Desenvolvimento

- O jogo foi desenvolvido em Godot utilizando GDScript.
- Ele faz requisições à API para autenticação e envio de dados de desempenho dos alunos.

## Funcionalidades

- **Login**
  - Login de professores.
  - Login de alunos.

- **Gestão de Fases**
  - Professores podem desbloquear e bloquear fases da sala de aula.
  - Alunos podem jogar as fases liberadas da sala de aula.

- **Personalização de Atividades**
  - Professores podem mudar as configurações de atividades das plataformas.

- **Envio de Estatísticas**
  - Os stats dos alunos são enviados à API.
  - A API armazena esses dados no MongoDB para análise e acompanhamento.


# Detalhes das Cenas e Recursos do Jogo

## Cenas

### Telas e Interfaces
- `UI.screen.tscn`: Cena principal da interface do usuário.
- `login.screen.tscn`: Cena de tela de login.
- `level-select.tscn`: Cena de seleção de nível.
- `game_over.screen.tscn`: Cena de tela de game over.
- `feedback.tscn`: Cena para feedback durante o jogo.
- `transition.tscn`: Cena de transição entre níveis.
- `paused.tscn`: Cena de pausa durante o jogo.
- `cutscene.tscn`: Cena para cutscenes no jogo.
- `prologue.cutscene.tscn`: Cena para cutscene de prólogo.
  
### Cenas de Ambiente e Fases
- `second_floor_neutros.scenario.tscn`: Cenário do segundo andar neutro.
- `roof_neutros.scenario.tscn`: Cenário do telhado neutro.
- `outside_neutros.scenario.tscn`: Cenário externo neutro.
- `outside_biodefensores.scenario.tscn`: Cenário externo biodefensores.
- `inside_biodefensores.scenario.tscn`: Cenário interno biodefensores.
- `first_floor_neutros.scenario.tscn`: Cenário do primeiro andar neutro.
- `saving_amazon_endless.scenario.tscn`: Cenário de salvar a Amazônia sem fim.
  
### Cenas Específicas de Jogabilidade
- `controlPlataforms.tscn`: Controle dos itens da plataforma, obtidos da API conforme definido no dashboard.
- `boss_01.tscn`: Cena do primeiro chefe do jogo.
- `azurea.tscn`: Cena usada no chefe para apagar fogo com baldes de água.
- `utils/set_objective.tscn`: Utilitário para definir objetivos no jogo.

### Recursos e Itens
- `platform.object.tscn`: Atividades personalizadas definidas pelo dashboard.
- `music.object.tscn`: Objeto que controla a música do jogo.
- `fire.object.tscn`: Objeto instanciado no chefe para representar fogo.
- `vida.tscn`: Representação da vida do chefe 01.
- `drone.tscn`: Cena de drone no jogo.
- `wiring_panel.item.tscn`: Item usado na fase 3 para painel de fiação.
- `lock.item.tscn`: Item usado na fase 1 para bloqueio.
- `guarana.tscn`: Item especial colecionável que concede invulnerabilidade.
- `coin.tscn`: Representação de moeda no jogo.
- `bucket.item.tscn`: Item usado por Azurea para apagar fogo no chefe.
- `biotech.item.tscn`: Item biotecnológico no jogo.

Cada uma dessas cenas e recursos descreve elementos específicos do jogo, desde ambientes e fases até itens e mecânicas especiais.
