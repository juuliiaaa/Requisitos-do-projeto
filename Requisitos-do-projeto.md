# SENAC
## BACHARELADO EM CIÊNCIA DA COMPUTAÇÃO
### JÚLIA ALMEIDA LEITE
### MARIA EDUARDA MARIANO COELHO

<br><br><br>

# REQUISITOS DO PROJETO: Rastreador de Fitness


## INTRODUÇÃO

O crescimento do interesse por saúde e bem-estar tem impulsionado o uso de aplicações digitais voltadas ao acompanhamento de atividades físicas. Nesse contexto, surge a necessidade de soluções que não apenas registrem exercícios, mas também promovam engajamento, acompanhamento de desempenho e interação entre usuários. O presente trabalho tem como estudo de caso o desenvolvimento do sistema FitTrack, uma plataforma digital de rastreamento de atividades físicas voltada tanto para indivíduos quanto para academias.

O FitTrack tem como objetivo permitir que usuários registrem suas atividades físicas, acompanhem sua evolução ao longo do tempo e participem de desafios que incentivem a prática contínua de exercícios. Além disso, o sistema oferece funcionalidades voltadas à gestão de academias, possibilitando o acompanhamento coletivo do desempenho dos alunos e a criação de estratégias de engajamento.

Para atender a esses objetivos, o sistema foi estruturado em três principais subsistemas. O primeiro, Gestão de Academia (SUB1), é responsável pelo cadastro e administração de academias e seus membros, oferecendo funcionalidades como controle de usuários, relatórios e comunicação. O segundo, Rastreamento de Atividades (SUB2), constitui o núcleo da aplicação, permitindo o registro, acompanhamento e análise de atividades físicas individuais. Por fim, o terceiro subsistema, Desafios e Comunidade (SUB3), tem como foco a gamificação da experiência, por meio da criação e participação em desafios, rankings e interações sociais entre usuários.

Os grupos de usuários do sistema são divididos em dois perfis principais: o Administrador da Academia, responsável pela gestão de academias e acompanhamento coletivo dos alunos, e o Atleta, que utiliza a plataforma para registrar suas atividades, acompanhar seu desempenho e interagir com outros usuários. Cada perfil possui necessidades específicas, o que orienta tanto a definição dos requisitos funcionais quanto dos requisitos não funcionais do sistema.

---

# 1. LEVANTAMENTO DOS REQUISITOS FUNCIONAIS

## 1.1 Histórias de Usuário

#### Gestão de Academia

| Campo                  | Descrição                                                                                                                                                                                     |
|------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ID                     | US-SUB1-001                                                                                                                                                                                   |
| História               | Como administrador da academia, eu quero cadastrar minha academia na plataforma, para que eu possa gerenciar meus alunos e acompanhar o progresso coletivo do grupo.                          |
| Critérios de Aceitação | 1. O sistema deve permitir informar nome, endereço e tipo da academia. 2. O cadastro deve ser confirmado por e-mail. 3. Após o cadastro, o administrador deve ter acesso ao painel de gestão. |
| Dependências           | Nenhuma                                                                                                                                                                                       |
| Fonte                  | Administrador da Academia (USER-001)                                                                                                                                                          |


| Campo                  | Descrição                                                                                                                                                                                                              |
|------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ID                     | US-SUB1-002                                                                                                                                                                                                            |
| História               | Como administrador da academia, eu quero cadastrar novos alunos vinculados à minha academia, para que eles possam registrar atividades e participar dos desafios do grupo.                                             |
| Critérios de Aceitação | 1. O administrador deve poder inserir nome, e-mail e dados básicos do aluno. 2. O aluno deve receber um convite por e-mail para ativar sua conta. 3. O aluno cadastrado deve aparecer na lista de membros da academia. |
| Dependências           | US-SUB1-001                                                                                                                                                                                                            |
| Fonte                  | Administrador da Academia (USER-001)                                                                                                                                                                                   |


| Campo                  | Descrição                                                                                                                                                                                                                             |
|------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ID                     | US-SUB1-003                                                                                                                                                                                                                           |
| História               | Como administrador da academia, eu quero remover um aluno da minha academia, para que membros inativos ou desvinculados não figurem nos relatórios e desafios do grupo.                                                               |
| Critérios de Aceitação | 1. O administrador deve poder selecionar e remover qualquer membro da lista. 2. O aluno removido perde acesso aos desafios exclusivos da academia. 3. O histórico de atividades do aluno deve ser preservado em sua conta individual. |
| Dependências           | US-SUB1-002                                                                                                                                                                                                                           |
| Fonte                  | Administrador da Academia (USER-001)                                                                                                                                                                                                  |


| Campo                  | Descrição                                                                                                                                                                                                             |
|------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ID                     | US-SUB1-004                                                                                                                                                                                                           |
| História               | Como administrador da academia, eu quero visualizar o relatório de atividades dos meus alunos, para que eu possa identificar quem está engajado e quem precisa de incentivo.                                          |
| Critérios de Aceitação | 1. O relatório deve exibir o número de atividades registradas por aluno no período selecionado. 2. Deve ser possível filtrar por período (semanal, mensal). 3. O relatório deve ser exportável em formato CSV ou PDF. |
| Dependências           | US-SUB1-002, US-SUB2-001                                                                                                                                                                                              |
| Fonte                  | Administrador da Academia (USER-001)                                                                                                                                                                                  |


| Campo                  | Descrição                                                                                                                                                                                                                                                    |
|------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ID                     | US-SUB1-005                                                                                                                                                                                                                                                  |
| História               | Como administrador da academia, eu quero enviar mensagens de motivação para todos os meus alunos, para que eu possa incentivar a continuidade da prática de exercícios.                                                                                      |
| Critérios de Aceitação | 1. O administrador deve poder redigir e enviar uma mensagem para todos os membros ou para membros selecionados. 2. A mensagem deve ser entregue como notificação no aplicativo. 3. O envio deve ser confirmado com uma contagem de destinatários alcançados. |
| Dependências           | US-SUB1-002                                                                                                                                                                                                                                                  |
| Fonte                  | Administrador da Academia (USER-001)                                                                                                                                                                                                                         |


| Campo                  | Descrição                                                                                                                                                              |
|------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ID                     | US-SUB1-006                                                                                                                                                            |
| História               | Como administrador da academia, eu quero editar os dados cadastrais da minha academia, para que as informações exibidas aos alunos estejam sempre atualizadas.         |
| Critérios de Aceitação | 1. O administrador deve poder alterar nome, endereço e descrição da academia. 2. As alterações devem ser salvas imediatamente e refletidas na visualização dos alunos. |
| Dependências           | US-SUB1-001                                                                                                                                                            |
| Fonte                  | Administrador da Academia (USER-001)                                                                                                                                   |


| Campo                  | Descrição                                                                                                                                                                                                                                  |
|------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ID                     | US-SUB1-007                                                                                                                                                                                                                                |
| História               | Como administrador da academia, eu quero visualizar um ranking de engajamento dos meus alunos, para que eu possa reconhecer e valorizar os membros mais ativos.                                                                            |
| Critérios de Aceitação | 1. O ranking deve ordenar os alunos por quantidade de atividades registradas no período. 2. Deve ser possível alternar entre ranking semanal e mensal. 3. O ranking deve exibir nome, foto (opcional) e total de atividades de cada aluno. |
| Dependências           | US-SUB1-002, US-SUB2-001                                                                                                                                                                                                                   |
| Fonte                  | Administrador da Academia (USER-001)                                                                                                                                                                                                       |


| Campo                  | Descrição                                                                                                                                                                                                                      |
|------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ID                     | US-SUB1-008                                                                                                                                                                                                                    |
| História               | Como administrador da academia, eu quero definir o tipo de atividades que serão contabilizadas nos relatórios do grupo, para que as estatísticas reflitam o foco de treino da minha academia.                                  |
| Critérios de Aceitação | 1. O administrador deve poder selecionar quais tipos de atividade (corrida, musculação, ciclismo, etc.) são contabilizados nos relatórios do grupo. 2. A configuração deve ser salva e aplicada a todos os relatórios futuros. |
| Dependências           | US-SUB1-001                                                                                                                                                                                                                    |
| Fonte                  | Administrador da Academia (USER-001)                                                                                                                                                                                           |


| Campo                  | Descrição                                                                                                                                                                                                    |
|------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ID                     | US-SUB1-009                                                                                                                                                                                                  |
| História               | Como administrador da academia, eu quero convidar um usuário já cadastrado na plataforma para minha academia, para que alunos existentes possam ser incorporados ao grupo sem precisar criar uma nova conta. |
| Critérios de Aceitação | 1. O administrador deve poder buscar usuários pelo e-mail cadastrado. 2. O sistema deve enviar um convite ao usuário encontrado. 3. O usuário deve poder aceitar ou recusar o convite.                       |
| Dependências           | US-SUB1-001                                                                                                                                                                                                  |
| Fonte                  | Administrador da Academia (USER-001)                                                                                                                                                                         |


| Campo                  | Descrição                                                                                                                                                                                                                                          |
|------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ID                     | US-SUB1-010                                                                                                                                                                                                                                        |
| História               | Como administrador da academia, eu quero visualizar um resumo geral do desempenho da academia, para que eu tenha uma visão consolidada do engajamento do grupo em um único painel.                                                                 |
| Critérios de Aceitação | 1. O painel deve exibir: total de membros ativos, total de atividades registradas no mês e tipo de exercício mais praticado. 2. Os dados devem ser atualizados em tempo real. 3. O painel deve ser a tela inicial do administrador ao fazer login. |
| Dependências           | US-SUB1-002, US-SUB2-001                                                                                                                                                                                                                           |
| Fonte                  | Administrador da Academia (USER-001)                                                                                                                                                                                                               |

---

#### Rastreamento de Atividades


| Campo                  | Descrição                                                                                                                                                                                                                                                                        |
|------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ID                     | US-SUB2-001                                                                                                                                                                                                                                                                      |
| História               | Como atleta, eu quero registrar uma atividade física informando tipo, duração e distância, para que eu tenha um histórico completo dos meus treinos.                                                                                                                             |
| Critérios de Aceitação | 1. O sistema deve oferecer os tipos: caminhada, corrida, ciclismo, musculação e outros. 2. Duração e distância devem ser campos obrigatórios para atividades de cardio; distância é opcional para musculação. 3. O registro deve ser salvo e exibido imediatamente no histórico. |
| Dependências           | Cadastro do atleta                                                                                                                                                                                                                                                               |
| Fonte                  | Atleta (USER-002)                                                                                                                                                                                                                                                                |


| Campo                  | Descrição                                                                                                                                                                                                                   |
|------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ID                     | US-SUB2-002                                                                                                                                                                                                                 |
| História               | Como atleta, eu quero visualizar a estimativa de calorias queimadas após registrar uma atividade, para que eu possa entender o impacto do meu treino no gasto energético diário.                                            |
| Critérios de Aceitação | 1. O cálculo deve considerar tipo de atividade, duração e dados do usuário (peso e altura). 2. O resultado deve ser exibido imediatamente após o registro. 3. O sistema deve deixar explícito que o valor é uma estimativa. |
| Dependências           | US-SUB2-001, US-SUB2-006                                                                                                                                                                                                    |
| Fonte                  | Atleta (USER-002)                                                                                                                                                                                                           |


| Campo                  | Descrição                                                                                                                                                                                                                                                   |
|------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ID                     | US-SUB2-003                                                                                                                                                                                                                                                 |
| História               | Como atleta, eu quero definir metas pessoais de distância, tempo ou calorias, para que eu tenha objetivos claros que orientem minha evolução física.                                                                                                        |
| Critérios de Aceitação | 1. O atleta deve poder criar metas com tipo (distância, tempo ou calorias), valor-alvo e prazo. 2. O sistema deve exibir o progresso em relação à meta sempre que uma atividade for registrada. 3. O atleta deve receber uma notificação ao atingir a meta. |
| Dependências           | US-SUB2-001                                                                                                                                                                                                                                                 |
| Fonte                  | Atleta (USER-002)                                                                                                                                                                                                                                           |


| Campo                  | Descrição                                                                                                                                                                                                                   |
|------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ID                     | US-SUB2-004                                                                                                                                                                                                                 |
| História               | Como atleta, eu quero visualizar gráficos de progresso semanal e mensal das minhas atividades, para que eu possa acompanhar minha evolução ao longo do tempo de forma visual.                                               |
| Critérios de Aceitação | 1. Os gráficos devem exibir distância, duração e calorias por período. 2. O atleta deve poder alternar entre visão semanal e mensal. 3. Os gráficos devem ser atualizados automaticamente a cada nova atividade registrada. |
| Dependências           | US-SUB2-001                                                                                                                                                                                                                 |
| Fonte                  | Atleta (USER-002)                                                                                                                                                                                                           |


| Campo                  | Descrição                                                                                                                                                                                                                           |
|------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ID                     | US-SUB2-005                                                                                                                                                                                                                         |
| História               | Como atleta, eu quero consultar o histórico completo de todas as minhas atividades registradas, para que eu possa revisar meus treinos anteriores e acompanhar minha consistência.                                                  |
| Critérios de Aceitação | 1. O histórico deve listar todas as atividades em ordem cronológica decrescente. 2. Deve ser possível filtrar por tipo de atividade e por período. 3. Cada entrada deve exibir data, tipo, duração, distância e calorias estimadas. |
| Dependências           | US-SUB2-001                                                                                                                                                                                                                         |
| Fonte                  | Atleta (USER-002)                                                                                                                                                                                                                   |


| Campo                  | Descrição                                                                                                                                                                                                                            |
|------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ID                     | US-SUB2-006                                                                                                                                                                                                                          |
| História               | Como atleta, eu quero informar meus dados físicos (peso e altura), para que o sistema calcule com maior precisão as calorias queimadas nas minhas atividades.                                                                        |
| Critérios de Aceitação | 1. O sistema deve disponibilizar campos de peso (kg) e altura (cm) no perfil do atleta. 2. O atleta deve poder atualizar esses dados a qualquer momento. 3. Qualquer alteração deve ser aplicada aos cálculos de atividades futuras. |
| Dependências           | Cadastro do atleta                                                                                                                                                                                                                   |
| Fonte                  | Atleta (USER-002)                                                                                                                                                                                                                    |


| Campo                  | Descrição                                                                                                                                                                                                                                                   |
|------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ID                     | US-SUB2-007                                                                                                                                                                                                                                                 |
| História               | Como atleta, eu quero editar ou excluir uma atividade registrada incorretamente, para que meu histórico e minhas estatísticas reflitam dados precisos.                                                                                                      |
| Critérios de Aceitação | 1. O atleta deve poder editar tipo, duração e distância de qualquer atividade registrada. 2. O atleta deve poder excluir uma atividade com confirmação da ação. 3. As estatísticas e gráficos devem ser recalculados imediatamente após edição ou exclusão. |
| Dependências           | US-SUB2-001                                                                                                                                                                                                                                                 |
| Fonte                  | Atleta (USER-002)                                                                                                                                                                                                                                           |


| Campo                  | Descrição                                                                                                                                                                                                                                     |
|------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ID                     | US-SUB2-008                                                                                                                                                                                                                                   |
| História               | Como atleta, eu quero importar dados de atividades do meu dispositivo wearable, para que eu não precise registrar manualmente os treinos já monitorados pelo meu relógio ou pulseira.                                                         |
| Critérios de Aceitação | 1. O sistema deve suportar importação via Google Fit e Apple Health. 2. Os dados importados devem seguir o mesmo padrão das atividades registradas manualmente. 3. O sistema deve evitar duplicação de registros já importados anteriormente. |
| Dependências           | US-SUB2-001                                                                                                                                                                                                                                   |
| Fonte                  | Atleta (USER-002)                                                                                                                                                                                                                             |



| Campo                  | Descrição                                                                                                                                                                                                                                     |
|------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ID                     | US-SUB2-009                                                                                                                                                                                                                                   |
| História               | Como atleta, eu quero visualizar o trajeto percorrido em atividades de corrida ou ciclismo no mapa, para que eu possa analisar minhas rotas e planejar novos percursos.                                                                       |
| Critérios de Aceitação | 1. O mapa deve exibir o trajeto registrado via GPS durante a atividade. 2. Deve ser possível visualizar distância e tempo em cada trecho do percurso. 3. A funcionalidade deve estar disponível apenas para atividades de corrida e ciclismo. |
| Dependências           | US-SUB2-001                                                                                                                                                                                                                                   |
| Fonte                  | Atleta (USER-002)                                                                                                                                                                                                                             |



| Campo                  | Descrição                                                                                                                                                                                                       |
|------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ID                     | US-SUB2-010                                                                                                                                                                                                     |
| História               | Como atleta, eu quero receber lembretes para registrar minhas atividades físicas, para que eu não esqueça de manter meu histórico atualizado e mantenha a consistência dos treinos.                             |
| Critérios de Aceitação | 1. O atleta deve poder configurar dias e horários para receber lembretes. 2. O lembrete deve ser enviado como notificação push no aplicativo. 3. O atleta deve poder desativar os lembretes a qualquer momento. |
| Dependências           | Cadastro do atleta                                                                                                                                                                                              |
| Fonte                  | Atleta (USER-002)                                                                                                                                                                                               |

---

#### Desafios e Comunidade


| Campo                  | Descrição                                                                                                                                                                                                                                                          |
|------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ID                     | US-SUB3-001                                                                                                                                                                                                                                                        |
| História               | Como administrador da academia, eu quero criar desafios para os membros da minha academia, para que eu possa estimular a competição saudável e aumentar o engajamento do grupo.                                                                                    |
| Critérios de Aceitação | 1. O administrador deve poder definir nome, descrição, tipo de métrica (distância, tempo ou calorias), meta e prazo do desafio. 2. O desafio deve ser visível apenas para os membros da academia. 3. O sistema deve notificar os membros ao criar um novo desafio. |
| Dependências           | US-SUB1-001, US-SUB2-001                                                                                                                                                                                                                                           |
| Fonte                  | Administrador da Academia (USER-001)                                                                                                                                                                                                                               |


| Campo                  | Descrição                                                                                                                                                                                                                                            |
|------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ID                     | US-SUB3-002                                                                                                                                                                                                                                          |
| História               | Como atleta, eu quero visualizar os desafios disponíveis para mim, para que eu possa escolher os que mais se adequam aos meus objetivos e participar deles.                                                                                          |
| Critérios de Aceitação | 1. A listagem deve exibir desafios da academia do atleta e desafios públicos. 2. Cada desafio deve mostrar nome, descrição, prazo e número de participantes. 3. Deve ser possível filtrar por tipo de atividade ou status (em andamento, encerrado). |
| Dependências           | US-SUB3-001                                                                                                                                                                                                                                          |
| Fonte                  | Atleta (USER-002)                                                                                                                                                                                                                                    |


| Campo                  | Descrição                                                                                                                                                                                                                                   |
|------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ID                     | US-SUB3-003                                                                                                                                                                                                                                 |
| História               | Como atleta eu quero me inscrever em um desafio, para que minhas atividades sejam contabilizadas automaticamente no progresso do desafio.                                                                                                   |
| Critérios de Aceitação | 1. A inscrição deve ser confirmada com uma mensagem de boas-vindas ao desafio. 2. As atividades registradas após a inscrição devem ser contabilizadas automaticamente. 3. O atleta não deve poder se inscrever duas vezes no mesmo desafio. |
| Dependências           | US-SUB3-002, US-SUB2-001                                                                                                                                                                                                                    |
| Fonte                  | Atleta (USER-002)                                                                                                                                                                                                                           |


| Campo                  | Descrição                                                                                                                                                                                                                                 |
|------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ID                     | US-SUB3-004                                                                                                                                                                                                                               |
| História               | Como atleta, eu quero acompanhar meu progresso e o ranking de um desafio em tempo real, para que eu saiba minha posição em relação aos outros participantes e me motive a continuar.                                                      |
| Critérios de Aceitação | 1. O ranking deve exibir todos os participantes ordenados pelo progresso na métrica do desafio. 2. A posição do atleta deve ser destacada na listagem. 3. O ranking deve ser atualizado automaticamente a cada nova atividade registrada. |
| Dependências           | US-SUB3-003                                                                                                                                                                                                                               |
| Fonte                  | Atleta (USER-002)                                                                                                                                                                                                                         |


| Campo                  | Descrição                                                                                                                                                                                                                          |
|------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ID                     | US-SUB3-005                                                                                                                                                                                                                        |
| História               | Como atleta, eu quero compartilhar o resultado de um desafio concluído, para que eu possa celebrar minha conquista com amigos e nas redes sociais.                                                                                 |
| Critérios de Aceitação | 1. O sistema deve gerar um card visual com o resultado do atleta no desafio. 2. Deve ser possível compartilhar via link ou diretamente nas redes sociais. 3. O card deve exibir nome do desafio, posição final e métrica atingida. |
| Dependências           | US-SUB3-003                                                                                                                                                                                                                        |
| Fonte                  | Atleta (USER-002)                                                                                                                                                                                                                  |


| Campo                  | Descrição                                                                                                                                                                                                            |
|------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ID                     | US-SUB3-006                                                                                                                                                                                                          |
| Hstória                | Como atleta, eu quero criar um desafio pessoal e convidar amigos para participar, para que eu possa competir de forma independente, sem necessidade de vínculo com uma academia.                                     |
| Critérios de Aceitação | 1. O atleta deve poder definir nome, métrica, meta e prazo do desafio. 2. O sistema deve gerar um link de convite para ser compartilhado com amigos. 3. O desafio criado deve ser visível apenas para os convidados. |
| Dependências           | US-SUB2-001                                                                                                                                                                                                          |
| Fonte                  | Atleta (USER-002)                                                                                                                                                                                                    |


| Campo                  | Descrição                                                                                                                                                                                                                                        |
|------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ID                     | US-SUB3-007                                                                                                                                                                                                                                      |
| História               | Como atleta, eu quero receber notificações sobre o andamento dos desafios em que participo, para que eu seja alertado quando outro participante ultrapassar minha posição no ranking.                                                            |
| Critérios de Aceitação | 1. O atleta deve receber notificação push quando for ultrapassado no ranking. 2. O atleta deve receber notificação quando o prazo do desafio estiver próximo do fim. 3. As notificações devem poder ser configuradas ou desativadas pelo atleta. |
| Dependências           | US-SUB3-003                                                                                                                                                                                                                                      |
| Fonte                  | Atleta (USER-002)                                                                                                                                                                                                                                |


| Campo                  | Descrição                                                                                                                                                                                                                                        |
|------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ID                     | US-SUB3-008                                                                                                                                                                                                                                      |
| História               | Como administrador da academia, eu quero encerrar um desafio antes do prazo, para que eu possa gerenciar os desafios do grupo de acordo com as necessidades da academia.                                                                         |
| Critérios de Aceitação | 1. Ao encerrar, o sistema deve exibir o ranking final e notificar todos os participantes. 2. O desafio encerrado deve ser movido para o histórico de desafios da academia. 3. Nenhuma nova atividade deve ser contabilizada após o encerramento. |
| Dependências           | US-SUB3-001                                                                                                                                                                                                                                      |
| Fonte                  | Administrador da Academia (USER-001)                                                                                                                                                                                                             |


| Campo                  | Descrição                                                                                                                                                                                                                                |
|------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ID                     | US-SUB3-009                                                                                                                                                                                                                              |
| História               | Como atleta, eu quero visualizar o histórico de desafios em que já participei, para que eu possa acompanhar minha evolução em competições ao longo do tempo.                                                                             |
| Critérios de Aceitação | 1. O histórico deve listar todos os desafios concluídos com data, posição final e métrica atingida. 2. Deve ser possível filtrar por tipo de atividade e período. 3. O atleta deve poder acessar o detalhe de qualquer desafio anterior. |
| Dependências           | US-SUB3-003                                                                                                                                                                                                                              |
| Fonte                  | Atleta (USER-002)                                                                                                                                                                                                                        |


| Campo                  | Descrição                                                                                                                                                                                                                    |
|------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ID                     | US-SUB3-010                                                                                                                                                                                                                  |
| História               | Como atleta, eu quero adicionar amigos na plataforma, para que eu possa acompanhar as atividades deles e criar desafios em conjunto.                                                                                         |
| Critérios de Aceitação | 1. O atleta deve poder buscar outros usuários pelo nome ou e-mail. 2. A adição de amigo deve ser confirmada pelo outro usuário. 3. Após confirmação, o atleta deve poder visualizar o resumo público de atividades do amigo. |
| Dependências           | Cadastro do atleta                                                                                                                                                                                                           |
| Fonte                  | Atleta (USER-002)                                                                                                                                                                                                            |

---

### 1.2 Estimativa de Tamanho

A metodologia adotada foi Story Points com escala Fibonacci (1, 2, 3, 5, 8, 13, 21).

O FitTrack é um projeto em estágio inicial, com equipe acadêmica de tamanho reduzido e escopo ainda em definição. Story Points são adequados a esse contexto por três razões principais:

1. Estimativa relativa: a escala Fibonacci força a comparação entre histórias em vez de estimativas absolutas de horas, o que é mais preciso para equipes sem histórico de velocidade estabelecido.
2. Reflete complexidade e incerteza juntos: cada ponto representa esforço, complexidade técnica e risco combinados — essencial para um sistema com integrações externas (mapas, wearables) cujo esforço real ainda é incerto.
3. Amplamente adotado em Scrum: como o trabalho segue práticas ágeis (histórias de usuário, critérios de aceitação), Story Points é a métrica naturalmente complementar.

**Critérios de pontuação aplicados:**

| Pontos | Perfil da história                                             |
|--------|----------------------------------------------------------------|
| 1–2    | CRUD simples, sem lógica de negócio complexa, sem integrações  |
| 3–5    | Lógica de negócio moderada, validações, múltiplas telas        |
| 8      | Integrações externas, cálculos, relacionamento entre entidades |
| 13     | Funcionalidades com múltiplas dependências e regras complexas  |
| 21     | Alta incerteza técnica, integrações de terceiros não testadas  |

### 1.3 Priorização com MoSCoW

#### Gestão de Academia

| Categoria | Descrição                                                                                                                                                                  |
|-----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| M         | Cadastrar academia na plataforma - Base de toda a estrutura multi-tenant do sistema; sem isso nenhum fluxo de academia funciona                                            |
| M         | Cadastrar alunos vinculados à academia - Pré-requisito para relatórios, desafios e acompanhamento coletivo                                                                 |
| S         | Remover aluno da academia - Importante para gestão, mas a ausência não impede o funcionamento do sistema                                                                   |
| M         | Visualizar relatório de atividades dos alunos - Principal entrega de valor para o administrador; justifica o uso da plataforma pela academia                               |
| S         | Enviar mensagens de motivação para alunos - Contribui para engajamento e retenção, mas não é bloqueante para o MVP                                                         |
| S         | Editar dados cadastrais da academia - Necessário para manutenção, mas não crítico para o lançamento                                                                        |
| S         | Visualizar ranking de engajamento dos alunos - Agrega valor competitivo à plataforma, mas pode ser entregue após o MVP básico                                              |
| C         | Definir tipos de atividade contabilizados nos relatórios - Personalização desejável, mas relatórios com todas as atividades já atendem a maioria dos casos                 |
| S         | Convidar usuário já cadastrado para a academia - Facilita a adoção por academias com alunos já na plataforma, mas o fluxo de convite por e-mail supre a necessidade no MVP |
| M         | Painel resumo geral da academia - Tela inicial do administrador; essencial para a experiência de uso da plataforma                                                         |

---

#### Rastreamento de Atividades

| Categoria | Descrição                                                                                                                                      |
|-----------|------------------------------------------------------------------------------------------------------------------------------------------------|
| M         | Registrar atividade física - Funcionalidade nuclear do produto; sem ela nenhum outro fluxo do SUB2 existe                                      |
| M         | Visualizar estimativa de calorias queimadas - Alto valor percebido pelo usuário; diferencial direto frente ao registro manual simples          |
| M         | Definir metas pessoais - Central para a proposta de valor do FitTrack; motivação e direcionamento do atleta                                    |
| M         | Visualizar gráficos de progresso - Principal elemento de retenção do usuário; evidencia evolução e justifica o uso contínuo                    |
| M         | Consultar histórico completo de atividades - Dado essencial para o atleta e para os relatórios do administrador                                |
| M         | Informar dados físicos (peso e altura) - Pré-requisito para o cálculo de calorias; baixa complexidade                                          |
| S         | Editar ou excluir atividade registrada - Importante para integridade dos dados, mas não bloqueia o funcionamento básico                        |
| W         | Importar dados de dispositivo wearable - Alta complexidade de integração com APIs proprietárias (Garmin, Apple, Google); fora do escopo do MVP |
| C         | Visualizar trajeto no mapa - Desejável e diferenciador, mas requer integração com serviço de mapas e GPS; pode ser entregue em versão futura   |
| S         | Receber lembretes para registrar atividades - Importante para formação de hábito e retenção, mas não bloqueia o funcionamento básico           |

---

#### Desafios e Comunidade

| Categoria | Descrição                                                                                                                                         |
|-----------|---------------------------------------------------------------------------------------------------------------------------------------------------|
| M         | Criar desafios para membros da academia - Principal ferramenta de engajamento do administrador; um dos diferenciais do FitTrack                   |
| M         | Visualizar desafios disponíveis - Pré-requisito para qualquer interação do atleta com o subsistema de desafios                                    |
| M         | Inscrever-se em um desafio - Sem inscrição, o atleta não participa e o subsistema não gera valor                                                  |
| M         | Acompanhar progresso e ranking em tempo real - Elemento central de gamificação; motivação principal para manter participação no desafio           |
| C         | Compartilhar resultado de desafio concluído - Agrega valor de marketing e engajamento social, mas não é essencial para o funcionamento do desafio |
| S         | Criar desafio pessoal e convidar amigos - Expande o produto para usuários independentes de academias; importante mas pode vir após o MVP          |
| S         | Receber notificações sobre andamento dos desafios - Aumenta engajamento e retenção nos desafios, mas não impede sua execução                      |
| S         | Encerrar desafio antes do prazo - Necessário para gestão operacional da academia, mas o prazo automático cobre a maioria dos casos                |
| C         | Visualizar histórico de desafios participados - Desejável para acompanhamento de evolução, mas não é crítico para o MVP                           |
| C         | Adicionar amigos na plataforma - Enriquece a experiência social, mas os desafios de academia já cobrem o aspecto comunitário no MVP               |

---

# 2. LEVANTAMENTO DOS REQUISITOS  NÃO FUNCIONAIS

## 2.1 Mapeamento de Requisitos Não Funcionais

#### Desempenho
- Tempo de resposta: O sistema deve responder a operações comuns (registro de atividade, carregamento do dashboard, exibição de gráficos) em até 2 segundos em condições normais de uso. Operações de geração de relatórios do administrador podem tolerar até 5 segundos. 
- Throughput: O sistema deve suportar ao menos 100 requisições por segundo nos horários de pico sem degradação perceptível nem erros de servidor (HTTP 5xx).
- Latência: A latência de rede entre o cliente e o servidor deve ser inferior a 300ms para 95% das requisições em condições normais. Operações de atualização de ranking em desafios devem ter latência máxima de 500ms para garantir a sensação de tempo real.

---

#### Escalabilidade
- Estimativa de acessos simultâneos: O sistema deve suportar ao menos 500 usuários simultâneos na fase inicial (1.000–5.000 usuários ativos mensais), considerando picos de acesso concentrados. A arquitetura deve ser dimensionada para escalar até 2.000 usuários simultâneos sem refatoração estrutural, prevendo crescimento do produto.
- Horários de pico de uso: Os dois principais picos de acesso esperados são o período matutino (6h–8h), com registros de treinos antes do trabalho, e o **período vespertino/noturno (17h–20h), com registros pós-trabalho. Fins de semana concentram atividades de corrida e ciclismo ao longo de toda a manhã. A infraestrutura deve ser dimensionada para suportar esses picos sem degradação. Diferença por subsistema: SUB2 (Rastreamento) é o mais crítico nos horários de pico; SUB1 (Gestão) concentra uso em horário comercial.
- Estratégia de crescimento: A arquitetura deve permitir **escalabilidade horizontal (adição de novas instâncias sem downtime) por meio de containers orquestrados. A separação do sistema em três subsistemas independentes (SUB1, SUB2, SUB3) favorece a adoção futura de uma arquitetura orientada a serviços, onde cada subsistema pode escalar de forma independente conforme a demanda.

---

#### Segurança
- Autenticação: O sistema deve exigir login com e-mail e senha. A senha deve ter no mínimo 8 caracteres, contendo letras, números e ao menos um caractere especial.
- Autorização: O sistema deve garantir isolamento total de dados por perfil: atletas acessam apenas seus próprios dados; administradores acessam apenas dados de sua academia; nenhum usuário pode acessar dados de outra academia.
- Proteção de dados — conformidade com a LGPD: Dados de saúde (peso, altura, histórico de atividades) são classificados como dados sensíveis pela Lei nº 13.709/2018 (LGPD), exigindo: (1) consentimento explícito antes da coleta; (2) funcionalidade de exclusão de conta e dados pessoais a pedido do titular; (3) política de privacidade acessível antes do cadastro. O não cumprimento sujeita o produto a sanções da ANPD.

---

#### Disponibilidade
- Uptime esperado: O sistema deve garantir disponibilidade mínima de 99,5% ao mês (equivalente a no máximo ~3,6 horas de indisponibilidade mensal). 
- Tolerância a falhas: Falhas em integrações externas (serviço de mapas, notificações push, APIs de wearables) não devem interromper o funcionamento do core do sistema. O registro manual de atividades deve operar de forma totalmente independente dessas integrações.

---

#### Usabilidade
- Acessibilidade: A interface deve seguir as diretrizes WCAG 2.1 nível AA para contraste de cores e legibilidade, garantindo uso por pessoas com baixa visão. 
- Curva de aprendizado: Um novo usuário deve completar o primeiro registro de atividade em até 3 cliques ou toques a partir da tela inicial, sem consultar documentação. 
- Padrões de interface por perfil: O Atleta (SUB2) demanda interface simplificada e otimizada para uso com uma mão em dispositivo móvel, logo após o treino. O Administrador (SUB1) tolera interface mais densa com mais informações por tela, pois opera principalmente em desktop durante horário comercial.

---

#### Portabilidade e Plataforma
- Critérios para plataforma web: O sistema deve funcionar corretamente nos navegadores Chrome, Safari e Firefox nas versões lançadas nos últimos 2 anos.
- Critérios para plataforma mobile: A interface deve ser responsiva e funcional em dispositivos. Prioridade para o Atleta (SUB2), que registra atividades no smartphone imediatamente após o treino.

---

#### Manutenibilidade
- Facilidade de atualização: O código deve ser organizado em módulos separados por subsistema, de forma que alterações em um subsistema não exijam modificações nos demais.
- Documentação técnica: O projeto deve manter documentação atualizada de: (1) arquitetura do sistema; (2) modelo de dados; (3) instruções de instalação e configuração do ambiente.

---

#### Critérios de Qualidade de Desenvolvimento
- Padrões de código: O projeto deve adotar um guia de estilo de código consistente.
- Cobertura de testes: O sistema deve manter cobertura mínima de 70% de testes unitários nas regras de negócio principais: cálculo de calorias (SUB2), controle de acesso (SUB1) e lógica de desafios (SUB3). 
- Integração contínua: O repositório deve ter uma pipeline de CI configurada que execute automaticamente os testes e a verificação de cobertura a cada pull request, bloqueando merges que reduzam a cobertura abaixo do mínimo definido.

---


## 2.2 Requisitos Diferenciados por Tipo de Usuário

Os requisitos não funcionais do FitTrack não são uniformes para todos os usuários e subsistemas. As diferenças mais relevantes estão descritas abaixo.

Em relação à segurança, o Administrador da Academia (SUB1) demanda o nível mais rigoroso, pois acessa dados de todos os membros do grupo — o que exige autenticação reforçada e registro de ações administrativas em log. O Atleta (SUB2), por sua vez, opera em isolamento individual: acessa apenas seus próprios dados e não tem visibilidade sobre outros usuários fora de desafios. No subsistema de Desafios e Comunidade (SUB3), o controle é misto — o ranking de um desafio é visível entre os participantes, mas o perfil pessoal e o histórico de atividades de cada atleta permanecem privados.

Em relação ao desempenho, o SUB2 exige a resposta mais rápida do sistema. O registro de atividade acontece logo após o treino, num contexto de atenção reduzida e uso em dispositivo móvel, o que torna inaceitável qualquer demora perceptível — daí o limite de 2 segundos. O SUB1 tolera tempos maiores para operações de relatório (até 5 segundos), pois o administrador acessa o sistema em contexto mais tranquilo, geralmente em desktop. O SUB3 exige baixa latência na atualização do ranking (até 3 segundos), para que a sensação de competição em tempo real seja preservada.

Em relação à disponibilidade, o SUB2 é o mais crítico nos horários de pico de treino — manhã cedo e fim de tarde —, quando a indisponibilidade causa perda direta de registros e frustra o hábito do usuário. O SUB1 concentra uso em horário comercial e tolera janelas de manutenção noturna com menor impacto. O SUB3 tem um ponto específico de criticidade: nos dias de encerramento de desafios, a disponibilidade deve ser garantida ao longo de todo o dia, já que participantes de diferentes regiões podem registrar atividades em horários variados.

Em relação à usabilidade, o Atleta precisa de uma interface simplificada, otimizada para uso com uma mão no smartphone, com o mínimo de toques possível para concluir o registro. O Administrador, que opera principalmente em desktop durante o horário de trabalho, tolera uma interface mais densa com mais informações por tela, como painéis de gestão, filtros e relatórios detalhados.

Em relação à portabilidade, o SUB2 prioriza dispositivos móveis, enquanto o SUB1 prioriza navegadores desktop. O SUB3 deve oferecer suporte completo a ambas as plataformas, pois tanto atletas (que acompanham rankings pelo celular) quanto administradores (que criam e gerenciam desafios pelo computador) interagem com ele.


## 2.3 Justificativa Baseada nos Aprendizados

ISO/IEC 25010 — Modelo de Qualidade de Produto de Software
Utilizado como estrutura principal de categorização. As oito características de qualidade do modelo (funcionalidade, desempenho, compatibilidade, usabilidade, confiabilidade, segurança, manutenibilidade e portabilidade) foram mapeadas diretamente na seção 2.1, garantindo cobertura sistemática e rastreável de todos os aspectos de qualidade relevantes para o FitTrack.

IEEE-830 — Especificação de Requisitos de Software
Os RNFs foram especificados seguindo o padrão IEEE-830: descrição precisa e mensurável, critério de verificação objetivo e rastreabilidade para subsistema e usuário de origem. O mesmo padrão foi aplicado nas restrições da ADO 1, garantindo consistência entre os dois documentos do projeto.

Princípios de Arquitetura de Software
As decisões de escalabilidade e manutenibilidade foram fundamentadas nos princípios de **baixo acoplamento, alta coesão** e **design for scale**, que orientam a separação do sistema em subsistemas independentes e a adoção de escalabilidade horizontal desde a fase de projeto.

LGPD — Lei Geral de Proteção de Dados (Lei nº 13.709/2018)
O requisito de segurança e conformidade foi integralmente fundamentado na LGPD. A classificação de dados de saúde como dados sensíveis impõe obrigações específicas — consentimento explícito, direito à exclusão e política de privacidade — que se traduzem diretamente em requisitos mensuráveis e verificáveis.

## 3.4 Formato de Documentação (Padrão IEEE-830)

#### Desempenho

**Tempo de resposta**

| Campo                  | Descrição                                                                                                                                                                                                      |
|------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Requisito ID           | NF-SUB2-001                                                                                                                                                                                                    |
| Título                 | Tempo de Resposta das Operações Principais                                                                                                                                                                     |
| Descrição              | O sistema deve responder a operações comuns (registro de atividade, carregamento do dashboard, exibição de gráficos) em até 2 segundos. Operações de relatórios do administrador podem tolerar até 5 segundos. |
| Entrada                | Requisição do usuário (ex.: salvar atividade, carregar dashboard, gerar relatório).                                                                                                                            |
| Processamento          | O sistema recebe a requisição, executa a lógica de negócio e consulta o banco de dados.                                                                                                                        |
| Saída                  | Resposta renderizada na interface do usuário dentro do limite de tempo definido.                                                                                                                               |
| Restrições             | Aplica-se a todas as operações em condições normais de uso com até 500 usuários simultâneos. Não inclui falhas de conectividade do lado do cliente.                                                            |
| Critérios de Aceitação | (a) 95% das requisições de registro e dashboard são atendidas em até 2s. (b) 95% das requisições de relatório são atendidas em até 5s. (c) Validado por teste de carga simulando 500 usuários simultâneos.     |


**Throughput**

| Campo                  | Descrição                                                                                                                                                |
|------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------|
| Requisito ID           | NF-SUB2-002                                                                                                                                              |
| Título                 | Capacidade de Processamento nos Horários de Pico                                                                                                         |
| Descrição              | O sistema deve suportar ao menos 100 requisições por segundo nos horários de pico sem degradação perceptível nem erros de servidor.                      |
| Entrada                | Conjunto de requisições simultâneas de múltiplos usuários nos períodos de pico.                                                                          |
| Processamento          | O servidor processa as requisições em paralelo, priorizando operações de registro de atividade.                                                          |
| Saída                  | Todas as requisições retornam resposta válida sem enfileiramento perceptível.                                                                            |
| Restrições             | Aplica-se exclusivamente aos horários de pico identificados. Fora desses períodos, o throughput mínimo esperado é de 30 req/s.                           |
| Critérios de Aceitação | (a) Sistema suporta 100 req/s sem erros HTTP 5xx. (b) Taxa de erro inferior a 0,1% durante os testes de carga. (c) Validado com ferramenta k6 ou JMeter. |


**Latência**

| Campo                  | Descrição                                                                                                                                                                            |
|------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Requisito ID           | NF-SUB2-003                                                                                                                                                                          |
| Título                 | Latência Máxima de Comunicação Cliente-Servidor                                                                                                                                      |
| Descrição              | A latência entre cliente e servidor deve ser inferior a 300ms para 95% das requisições em condições normais. Atualizações de ranking em desafios devem ter latência máxima de 500ms. |
| Entrada                | Requisição enviada pelo cliente (navegador ou app mobile) ao servidor da aplicação.                                                                                                  |
| Processamento          | O servidor processa a requisição e envia a resposta pelo menor caminho disponível na infraestrutura.                                                                                 |
| Saída                  | Resposta recebida pelo cliente dentro do limite de latência definido.                                                                                                                |
| Restrições             | Medido do lado do servidor. Latência de rede do provedor de internet do usuário não está sob controle do sistema.                                                                    |
| Critérios de Aceitação | (a) 95% das requisições gerais com latência abaixo de 300ms. (b) Atualizações de ranking com latência abaixo de 500ms. (c) Medido via ferramentas de APM.                            |


---

#### Escalabilidade

**Estimativa de acessos simultâneos**

| Campo                  | Descrição                                                                                                                                                               |
|------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Requisito ID | NF-SUB1-001                                                                                                                                                                       |
| Título                 | Capacidade Mínima de Usuários Simultâneos                                                                                                                               |
| Descrição              | O sistema deve suportar ao menos 500 usuários simultâneos na fase inicial, escalando para 2.000 sem necessidade de refatoração estrutural.                              |
| Entrada                | Acessos simultâneos de atletas e administradores distribuídos nos três subsistemas.                                                                                     |
| Processamento          | O servidor distribui as requisições entre instâncias disponíveis conforme a carga atual.                                                                                |
| Saída                  | Todas as sessões ativas respondem dentro dos limites de desempenho definidos (seção 2.1).                                                                               |
| Restrições             | A estimativa considera 1.000–5.000 usuários ativos mensais com concentração nos horários de pico.                                                                       |
| Critérios de Aceitação | (a) Sistema opera sem degradação com 500 usuários simultâneos. (b) Arquitetura permite escalar para 2.000 sem refatoração. (c) Validado via teste de carga progressivo. |


**Horários de pico de uso**

| Campo                  | Descrição                                                                                                                                                                             |
|------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Requisito ID           | NF-SUB2-004                                                                                                                                                                           |
| Título                 | Suporte a Horários de Pico de Uso                                                                                                                                                     |
| Descrição              | A infraestrutura deve suportar os dois picos diários de acesso sem degradação: período matutino e período vespertino/noturno. Fins de semana concentram uso ao longo de toda a manhã. |
| Entrada                | Aumento de requisições simultâneas nos períodos de pico identificados.                                                                                                                |
| Processamento          | O sistema provisiona recursos adicionais automaticamente ao detectar aumento de carga.                                                                                                |
| Saída                  | Tempo de resposta e throughput mantidos dentro dos limites definidos na seção 5.1 durante os picos.                                                                                   |
| Restrições             | SUB2 (Rastreamento) é o subsistema mais crítico nos picos; SUB1 (Gestão) concentra uso em horário comercial e tolera variações maiores.                                               |
| Critérios de Aceitação | (a) Métricas de desempenho mantidas durante simulação de pico com 100 req/s. (b) Nenhum erro HTTP 5xx registrado durante os períodos de pico nos primeiros 3 meses de operação.       |


**Estratégia de crescimento**

| Campo                  | Descrição                                                                                                                                                                                                                 |
|------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Requisito ID           | NF-SUB1-002                                                                                                                                                                                                               |
| Título                 | Escalabilidade Horizontal da Arquitetura                                                                                                                                                                                  |
| Descrição              | A arquitetura deve permitir escalabilidade horizontal por meio de containers orquestrados, possibilitando adição de instâncias sem downtime. Cada subsistema (SUB1, SUB2, SUB3) deve poder escalar de forma independente. |
| Entrada                | Aumento contínuo na base de usuários e no volume de dados registrados.                                                                                                                                                    |
| Processamento          | Novas instâncias são adicionadas ao pool de servidores sem interrupção do serviço, balanceando a carga entre elas.                                                                                                        |
| Saída                  | Capacidade do sistema ampliada sem indisponibilidade para os usuários ativos.                                                                                                                                             |
| Restrições             | A estratégia deve ser implementável com ferramentas de nuvem acessíveis ao orçamento do projeto (ex.: serviços gerenciados como Railway, Render ou AWS ECS).                                                              |
| Critérios de Aceitação | (a) Adição de nova instância sem causar downtime. (b) Separação de módulos por subsistema verificada na revisão de arquitetura. (c) Deploy automatizado configurado via pipeline de CI/CD.                                |


---

#### Segurança

**Autenticação**

| Campo                  | Descrição                                                                                                                                                                                                          |
|------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Requisito ID           | NF-SUB1-003                                                                                                                                                                                                        |
| Título                 | Autenticação de Usuários                                                                                                                                                                                           |
| Descrição              | O sistema deve exigir login com e-mail e senha de no mínimo 8 caracteres (letras, números e caractere especial). Senhas devem ser armazenadas com hash seguro.                                                     |
| Entrada                | Credenciais inseridas pelo usuário na tela de login (e-mail e senha).                                                                                                                                              |
| Processamento          | O sistema valida o e-mail, aplica hash na senha e compara com o registro armazenado. Em caso de sucesso, gera um token de sessão autenticado.                                                                      |
| Saída                  | Token de sessão válido ou mensagem de erro em caso de credenciais inválidas.                                                                                                                                       |
| Restrições             | Aplica-se a todos os perfis de usuário (Atleta e Administrador). Senhas não podem ser armazenadas em texto puro em nenhuma camada do sistema.                                                                      |
| Critérios de Aceitação | (a) Login bem-sucedido com credenciais válidas. (b) Login negado com credenciais inválidas, sem revelar qual campo está errado. (c) Revisão de código confirma uso de bcrypt ou Argon2 no armazenamento de senhas. |


**Autorização**

| Campo                  | Descrição                                                                                                                                                                                                                                    |
|------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Requisito ID           | NF-SUB1-004                                                                                                                                                                                                                                  |
| Título                 | Controle de Acesso e Isolamento de Dados                                                                                                                                                                                                     |
| Descrição              | O sistema deve garantir isolamento total de dados por perfil: atletas acessam apenas seus próprios dados; administradores acessam apenas dados de sua academia. Nenhum usuário pode acessar dados de outra academia ou de outro atleta.      |
| Entrada                | Requisição autenticada de um usuário tentando acessar um recurso do sistema.                                                                                                                                                                 |
| Processamento          | O sistema verifica o perfil e o escopo do token de sessão antes de processar qualquer operação de leitura ou escrita.                                                                                                                        |
| Saída                  | Dado retornado se o usuário tem permissão; erro HTTP 403 (Forbidden) se não tiver.                                                                                                                                                           |
| Restrições             | No SUB3, dados de ranking são visíveis entre participantes de um mesmo desafio, mas o perfil pessoal e o histórico completo de cada atleta permanecem privados.                                                                              |
| Critérios de Aceitação | (a) Usuário A não consegue acessar dados do usuário B (testado via requisição direta à API). (b) Administrador de academia X não visualiza dados da academia Y. (c) Erro HTTP 403 retornado em todas as tentativas de acesso não autorizado. |


**Proteção de dados — conformidade com a LGPD**

| Campo                  | Descrição                                                                                                                                                                                                                                                      |
|------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Requisito ID           | NF-SUB1-005                                                                                                                                                                                                                                                    |
| Título                 | Conformidade com a LGPD                                                                                                                                                                                                                                        |
| Descrição              | O sistema deve implementar: (1) consentimento explícito antes da coleta de dados de saúde; (2) funcionalidade de exclusão de conta e dados pessoais a pedido do titular; (3) política de privacidade acessível antes do cadastro.                              |
| Entrada                | Ação do usuário de criar conta, solicitar exclusão de dados ou acessar a política de privacidade.                                                                                                                                                              |
| Processamento          | No cadastro, o sistema exibe termo de consentimento e só prossegue após confirmação. Na exclusão, remove todos os dados pessoais do titular de forma irreversível.                                                                                             |
| Saída                  | Conta criada com registro de consentimento; dados excluídos permanentemente mediante solicitação.                                                                                                                                                              |
| Restrições             | Dados de saúde (peso, altura, histórico de atividades) são classificados como dados sensíveis pela Lei nº 13.709/2018 (LGPD) e exigem tratamento diferenciado.                                                                                                 |
| Critérios de Aceitação | (a) Tela de consentimento presente no fluxo de cadastro antes de qualquer coleta de dado. (b) Funcionalidade de exclusão de conta remove todos os dados do titular em até 30 dias. (c) Checklist de conformidade LGPD aplicado e aprovado antes do lançamento. |


---

#### Disponibilidade

**Uptime esperado**

| Campo                  | Descrição                                                                                                                                                                                                        |
|------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Requisito ID           | NF-SUB2-005                                                                                                                                                                                                      |
| Título                 | Disponibilidade Mínima do Sistema                                                                                                                                                                                |
| Descrição              | O sistema deve garantir disponibilidade mínima de 99,5% ao mês, equivalente a no máximo ~3,6 horas de indisponibilidade mensal.                                                                                  |
| Entrada                | Qualquer requisição de usuário ao sistema em qualquer horário do dia.                                                                                                                                            |
| Processamento          | O sistema mantém instâncias ativas e monitora sua saúde continuamente, reiniciando automaticamente instâncias com falha.                                                                                         |
| Saída                  | Resposta válida do sistema para o usuário; em caso de manutenção programada, exibição de página informativa.                                                                                                     |
| Restrições             | Janelas de manutenção programada devem ocorrer preferencialmente entre 2h e 5h, fora dos horários de pico. O SUB2 não deve ter indisponibilidade nos períodos de pico de treino.                                 |
| Critérios de Aceitação | (a) Uptime mensal ≥ 99,5% medido por ferramenta de monitoramento. (b) Nenhuma indisponibilidade não planejada superior a 1 hora contínua. (c) Relatório mensal de disponibilidade gerado e revisado pela equipe. |


**Tolerância a falhas**

| Campo                  | Descrição                                                                                                                                                                                                                                                                 |
|------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Requisito ID           | NF-SUB2-006                                                                                                                                                                                                                                                               |
| Título                 | Tolerância a Falhas em Integrações Externas                                                                                                                                                                                                                               |
| Descrição              | Falhas em integrações externas (serviço de mapas, notificações push, APIs de wearables) não devem interromper o funcionamento do core do sistema. O registro manual de atividades deve operar de forma totalmente independente.                                           |
| Entrada                | Falha ou indisponibilidade de um serviço externo integrado ao sistema.                                                                                                                                                                                                    |
| Processamento          | O sistema detecta a falha na integração externa, registra o erro em log e continua operando com as funcionalidades que não dependem desse serviço.                                                                                                                        |
| Saída                  | Funcionalidade core disponível normalmente; mensagem informativa ao usuário sobre a indisponibilidade parcial do recurso afetado.                                                                                                                                         |
| Restrições             | Aplica-se às integrações dos subsistemas SUB2 e SUB3. A falha de notificações push não deve impedir o registro de atividades nem a participação em desafios.                                                                                                              |
| Critérios de Aceitação | (a) Com API de mapas indisponível, o registro de atividade é concluído normalmente sem exibição de rota. (b) Com serviço de notificações indisponível, os dados de atividade são salvos corretamente. (c) Validado por testes de falha simulada nas integrações externas. |


---

#### Usabilidade

**Acessibilidade**

| Campo                  | Descrição                                                                                                                                                                                                                |
|------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Requisito ID           | NF-SUB2-007                                                                                                                                                                                                              |
| Título                 | Acessibilidade Visual da Interface                                                                                                                                                                                       |
| Descrição              | A interface deve seguir as diretrizes WCAG 2.1 nível AA, garantindo contraste mínimo de 4,5:1 para texto normal e legibilidade adequada para pessoas com baixa visão.                                                    |
| Entrada                | Acesso de qualquer usuário à interface do sistema em qualquer dispositivo.                                                                                                                                               |
| Processamento          | O sistema renderiza a interface respeitando as definições de contraste, tamanho de fonte e hierarquia visual estabelecidas no guia de estilos.                                                                           |
| Saída                  | Interface legível e navegável por usuários com diferentes capacidades visuais.                                                                                                                                           |
| Restrições             | Aplica-se a todos os subsistemas e perfis de usuário. Componentes de terceiros integrados à interface também devem respeitar os critérios de contraste.                                                                  |
| Critérios de Aceitação | (a) Contraste mínimo de 4,5:1 em todos os textos verificado com Lighthouse ou axe. (b) Nenhum elemento interativo principal acessível apenas por cor. (c) Validação automatizada na pipeline de CI antes de cada deploy. |


**Curva de aprendizado**

| Campo                  | Descrição                                                                                                                                                                                                                                 |
|------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Requisito ID           | NF-SUB2-008                                                                                                                                                                                                                               |
| Título                 | Eficiência do Fluxo de Registro de Atividade                                                                                                                                                                                              |
| Descrição              | Um novo usuário deve conseguir completar o primeiro registro de atividade em até 3 cliques ou toques a partir da tela inicial, sem necessidade de consultar documentação ou tutoriais.                                                    |
| Entrada                | Primeiro acesso de um novo atleta ao sistema após o cadastro.                                                                                                                                                                             |
| Processamento          | O sistema apresenta o fluxo de registro de forma direta na tela inicial, sem etapas intermediárias desnecessárias.                                                                                                                        |
| Saída                  | Atividade registrada com sucesso com no máximo 3 interações do usuário.                                                                                                                                                                   |
| Restrições             | Aplica-se ao SUB2 (Rastreamento de Atividades) no perfil de Atleta. O fluxo do Administrador (SUB1) pode exigir mais etapas dado o maior volume de informações.                                                                           |
| Critérios de Aceitação | (a) 5 usuários novos conseguem concluir o primeiro registro em até 3 toques em teste de usabilidade. (b) Nenhum usuário do teste consulta documentação durante a tarefa. (c) Tempo médio para o primeiro registro inferior a 60 segundos. |


**Padrões de interface**

| Campo                  | Descrição                                                                                                                                                                                    |
|------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Requisito ID           | NF-SUB1-006                                                                                                                                                                                  |
| Título                 | Adequação da Interface ao Contexto de Uso por Perfil                                                                                                                                         |
| Descrição              | A interface deve ser adaptada ao contexto de uso de cada perfil: Atleta com interface simplificada e otimizada para mobile; Administrador com interface mais densa adequada a desktop.       |
| Entrada                | Login do usuário com seu respectivo perfil (Atleta ou Administrador).                                                                                                                        |
| Processamento          | O sistema identifica o perfil autenticado e renderiza o layout correspondente ao contexto de uso esperado.                                                                                   |
| Saída                  | Interface adequada ao perfil exibida após o login.                                                                                                                                           |
| Restrições             | A diferenciação de interface não deve criar inconsistências visuais entre os subsistemas acessíveis por ambos os perfis (ex.: tela de desafios do SUB3).                                     |
| Critérios de Aceitação | (a) Interface do Atleta operável com uma mão em smartphone de 360px validada em teste de dispositivo. (b) Interface do Administrador exibe painel completo sem scroll horizontal em desktop. |

---

#### Portabilidade/Plataforma

**Critérios para plataforma web**

| Campo                  | Descrição                                                                                                                                                                                       |
|------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Requisito ID           | NF-SUB1-007                                                                                                                                                                                     |
| Título                 | Compatibilidade com Navegadores Web                                                                                                                                                             |
| Descrição              | O sistema deve funcionar corretamente nos navegadores Chrome, Safari e Firefox nas versões lançadas nos últimos 2 anos, sem perda de funcionalidade ou quebra de layout.                        |
| Entrada                | Acesso ao sistema via navegador web em dispositivo desktop ou tablet.                                                                                                                           |
| Processamento          | O sistema renderiza a interface utilizando padrões web compatíveis sem dependências de APIs descontinuadas.                                                                                     |
| Saída                  | Interface completamente funcional e visualmente consistente nos três navegadores.                                                                                                               |
| Restrições             | Prioridade para o perfil de Administrador (SUB1), que tende a acessar a plataforma em desktop. Navegadores com participação de mercado inferior a 1% não são cobertos.                          |
| Critérios de Aceitação | (a) Todos os fluxos principais executados sem erros nos três navegadores. (b) Nenhum elemento de layout quebrado em resolução 1280px. (c) Validado com testes automatizados de compatibilidade. |


**Critérios para plataforma mobile**

| Campo                  | Descrição                                                                                                                                                                                               |
|------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Requisito ID           | NF-SUB2-009                                                                                                                                                                                             |
| Título                 | Responsividade em Dispositivos Móveis                                                                                                                                                                   |
| Descrição              | A interface deve ser responsiva e totalmente funcional em dispositivos com telas a partir de 360px de largura, sem perda de funcionalidade ou necessidade de zoom manual.                               |
| Entrada                | Acesso ao sistema via navegador mobile ou app em smartphone com tela de 360px ou maior.                                                                                                                 |
| Processamento          | O sistema aplica layout responsivo (CSS Flexbox/Grid ou framework responsivo) adaptando os componentes ao tamanho da tela disponível.                                                                   |
| Saída                  | Interface adaptada ao dispositivo, com todos os elementos interativos acessíveis sem zoom ou scroll horizontal.                                                                                         |
| Restrições             | Prioridade para o perfil de Atleta (SUB2), que registra atividades no smartphone imediatamente após o treino.                                                                                           |
| Critérios de Aceitação | (a) Todos os fluxos do Atleta executados sem problemas em dispositivo de 360px. (b) Nenhum scroll horizontal em qualquer tela. (c) Testado em matriz de dispositivos cobrindo mobile, tablet e desktop. |


---

#### Manutenibilidade

**Facilidade de atualização**

| Campo                  | Descrição                                                                                                                                                                                   |
|------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Requisito ID           | NF-SUB1-008                                                                                                                                                                                 |
| Título                 | Modularidade da Arquitetura por Subsistema                                                                                                                                                  |
| Descrição              | O código deve ser organizado em módulos separados por subsistema (SUB1, SUB2, SUB3), de forma que alterações em um módulo não exijam modificações nos demais.                               |
| Entrada                | Necessidade de alteração, correção ou evolução de uma funcionalidade em qualquer subsistema.                                                                                                |
| Processamento          | O desenvolvedor modifica apenas o módulo do subsistema afetado, sem necessidade de alterar código de outros módulos.                                                                        |
| Saída                  | Funcionalidade atualizada sem regressão nos outros subsistemas.                                                                                                                             |
| Restrições             | Comunicação entre subsistemas deve ocorrer por interfaces bem definidas (ex.: chamadas de serviço ou eventos), nunca por acesso direto a módulos internos de outro subsistema.              |
| Critérios de Aceitação | (a) Revisão de arquitetura confirma ausência de dependências cruzadas diretas entre módulos de subsistemas distintos. (b) Alteração em SUB1 não quebra testes automatizados de SUB2 e SUB3. |


**Documentação técnica**

| Campo                  | Descrição                                                                                                                                                                                                           |
|------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Requisito ID           | NF-SUB1-009                                                                                                                                                                                                         |
| Título                 | Documentação Técnica do Projeto                                                                                                                                                                                     |
| Descrição              | O projeto deve manter documentação atualizada de: (1) arquitetura do sistema; (2) modelo de dados; (3) instruções de instalação e configuração do ambiente de desenvolvimento.                                      |
| Entrada                | Necessidade de onboarding de novo membro na equipe ou de configuração de novo ambiente.                                                                                                                             |
| Processamento          | O desenvolvedor consulta a documentação no repositório e configura o ambiente seguindo as instruções sem necessidade de suporte adicional.                                                                          |
| Saída                  | Ambiente de desenvolvimento funcional configurado a partir da documentação em até 30 minutos.                                                                                                                       |
| Restrições             | A documentação deve estar versionada junto ao código no repositório Git e atualizada a cada entrega.                                                                                                                |
| Critérios de Aceitação | (a) Novo membro da equipe consegue configurar o ambiente em até 30 minutos seguindo a documentação. (b) Documentação de arquitetura e modelo de dados presente e atualizada no repositório na data de cada entrega. |


---

#### Critérios de qualidade de desenvolvimento

**Padrões de código**

| Campo                  | Descrição                                                                                                                                      |
|------------------------|------------------------------------------------------------------------------------------------------------------------------------------------|
| Requisito ID           | NF-SUB1-010                                                                                                                                    |
| Título                 | Padronização de Estilo de Código                                                                                                               |
| Descrição              | O projeto deve adotar um guia de estilo de código consistente, aplicado e verificado automaticamente na pipeline de CI.                        |
| Entrada                | Pull request submetido por qualquer membro da equipe ao repositório principal.                                                                 |
| Processamento          | A pipeline de CI executa o linter automaticamente e bloqueia o merge caso violações de estilo sejam encontradas.                               |
| Saída                  | Código integrado ao repositório principal segue o guia de estilo definido sem exceções.                                                        |
| Restrições             | O guia de estilo deve ser definido e documentado no início do projeto. Exceções pontuais devem ser aprovadas em revisão de código.             |
| Critérios de Aceitação | (a) Pipeline de CI configurada com linter ativo em todos os pull requests. (b) Nenhum merge aprovado com violações de estilo não justificadas. |

---

**Cobertura de testes**

| Campo                  | Descrição                                                                                                                                                                                                                                       |
|------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Requisito ID           | NF-SUB2-010                                                                                                                                                                                                                                     |
| Título                 | Cobertura Mínima de Testes Unitários                                                                                                                                                                                                            |
| Descrição              | O sistema deve manter cobertura mínima de 70% de testes unitários nas regras de negócio principais: cálculo de calorias (SUB2), controle de acesso (SUB1) e lógica de desafios (SUB3).                                                          |
| Entrada                | Execução da suite de testes automatizados na pipeline de CI.                                                                                                                                                                                    |
| Processamento          | A ferramenta de cobertura analisa quais linhas de código das regras de negócio são exercitadas pelos testes e gera relatório percentual.                                                                                                        |
| Saída                  | Relatório de cobertura com percentual por módulo; pipeline bloqueia merge se cobertura cair abaixo de 70% nos módulos críticos.                                                                                                                 |
| Restrições             | A meta de 70% aplica-se exclusivamente às regras de negócio. Código de infraestrutura, configuração e interface não é obrigatoriamente coberto.                                                                                                 |
| Critérios de Aceitação | (a) Relatório de cobertura gerado automaticamente a cada pull request. (b) Cobertura ≥ 70% nos módulos de cálculo de calorias, controle de acesso e lógica de desafios. (c) Merge bloqueado automaticamente se cobertura cair abaixo do mínimo. |

---

**Integração contínua**

| Campo                  | Descrição                                                                                                                                                                                                   |
|------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Requisito ID           | NF-SUB1-011                                                                                                                                                                                                 |
| Título                 | Pipeline de Integração Contínua                                                                                                                                                                             |
| Descrição              | O repositório deve ter uma pipeline de CI configurada que execute automaticamente linting, testes e verificação de cobertura a cada pull request.                                                           |
| Entrada                | Pull request aberto ou atualizado no repositório principal.                                                                                                                                                 |
| Processamento          | A pipeline executa sequencialmente: (1) verificação de estilo; (2) testes unitários; (3) relatório de cobertura. Qualquer falha bloqueia o merge.                                                           |
| Saída                  | Status de aprovação ou reprovação da pipeline exibido no pull request. Merge liberado apenas com todos os checks verdes.                                                                                    |
| Restrições             | A pipeline deve ser executada em menos de 5 minutos para não atrasar o fluxo de desenvolvimento da equipe.                                                                                                  |
| Critérios de Aceitação | (a) Pipeline configurada e ativa no repositório desde a primeira entrega. (b) 100% dos merges para a branch principal passaram pela pipeline. (c) Tempo médio de execução da pipeline inferior a 5 minutos. |


---

# REFERÊNCIAS

IEEE COMPUTER SOCIETY.  
**IEEE Std 830-1998 — Recommended Practice for Software Requirements Specifications**. New York: IEEE, 1998.

SOMMERVILLE, Ian.  
**Engenharia de Software**. 10. ed. São Paulo: Pearson, 2019.

BRASIL.  
**Lei nº 13.709, de 14 de agosto de 2018 (Lei Geral de Proteção de Dados Pessoais — LGPD)**. Brasília, 2018.  
Disponível em: <https://www.planalto.gov.br>. Acesso em: 2026.

WORLD WIDE WEB CONSORTIUM (W3C).  
**Web Content Accessibility Guidelines (WCAG) 2.1**. 2018.  
Disponível em: <https://www.w3.org/TR/WCAG21/>. Acesso em: 2026.

Red Hat. 
O que são containers? Disponível em: <https://www.redhat.com/pt-br/topics/containers>. Acesso em: 2026.