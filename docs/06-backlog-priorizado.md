# 6. Backlog Priorizado

**Critério:** MoSCoW + valor para o usuário + dependência técnica. **Estimativa:** pontos de história (Fibonacci).
**Épicos:** E1 Acesso · E2 Questões · E3 Simulados · E4 Gabarito · E5 Estatísticas · E6 Fórum · E7 Administração

| Ordem | ID | User Story | Épico | Prior. | Pts | Requisitos |
|------:|----|-----------|-------|:------:|:---:|-----------|
| 1 | US01 | Como estudante, quero me cadastrar para acessar a plataforma | E1 | Must | 3 | RF01, RN02 |
| 2 | US02 | Como usuário, quero fazer login para acessar minhas funcionalidades | E1 | Must | 3 | RF02, RF04, RN15 |
| 3 | US03 | Como administrador, quero cadastrar e importar questões para manter o banco atualizado | E7 | Must | 8 | RF09, RN03, RN04 |
| 4 | US04 | Como estudante, quero filtrar questões por ano, curso e componente para estudar o que importa | E2 | Must | 5 | RF05, RF06 |
| 5 | US05 | Como estudante, quero responder uma questão e ver se acertei | E2 | Must | 3 | RF07 |
| 6 | US06 | Como estudante, quero ver o gabarito comentado para entender meu erro | E4 | Must | 3 | RF10, RN06 |
| 7 | US07 | Como estudante, quero gerar um simulado cronometrado para treinar de forma realista | E3 | Must | 8 | RF12, RF13, RN07 |
| 8 | US08 | Como estudante, quero ver minha nota e revisão ao final do simulado | E3 | Must | 5 | RF15, RN08 |
| 9 | US09 | Como estudante, quero ver meu desempenho por área para saber onde melhorar | E5 | Must | 5 | RF16, RN10 |
| 10 | US10 | Como estudante, quero discutir uma questão no fórum para aprender com colegas | E6 | Must | 5 | RF19, RN12 |
| 11 | US11 | Como moderador, quero ocultar/remover conteúdo inadequado | E6 | Must | 3 | RF21 |
| 12 | US12 | Como administrador, quero gerenciar usuários | E7 | Must | 3 | RF23 |
| 13 | US13 | Como estudante, quero recuperar minha senha | E1 | Should | 2 | RF03 |
| 14 | US14 | Como professor, quero comentar questões para apoiar os estudantes | E4 | Should | 5 | RF11, RN14 |
| 15 | US15 | Como estudante, quero retomar um simulado interrompido | E3 | Should | 5 | RF14, RN18 |
| 16 | US16 | Como estudante, quero ver a evolução do meu desempenho no tempo | E5 | Should | 3 | RF17 |
| 17 | US17 | Como coordenador, quero ver o desempenho agregado do curso | E5 | Should | 8 | RF18, RN11 |
| 18 | US18 | Como usuário, quero denunciar conteúdo inadequado | E6 | Should | 2 | RF20, RN13 |
| 19 | US19 | Como estudante, quero favoritar questões para revisar depois | E2 | Could | 2 | RF08 |
| 20 | US20 | Como usuário, quero ser notificado sobre respostas aos meus tópicos | E6 | Could | 3 | RF22 |
| 21 | US21 | Como administrador, quero ver indicadores de uso da plataforma | E7 | Could | 5 | RF24 |
| — | US22 | Aplicativo nativo iOS/Android | — | Won't | — | — |
| — | US23 | Integração com sistemas acadêmicos da instituição | — | Won't | — | — |

## Plano por sprint
| Sprint | Foco | Itens |
|--------|------|-------|
| Sprint 1 (M1) | Elicitação e UML | Visão, stakeholders, entrevistas, requisitos, regras, backlog, UML |
| Sprint 2 (M2) | Especificação e protótipo | SRS (IEEE 830), consistência UML/SRS, wireframes, protótipo navegável |
| Sprint 3 (M3) | Pitch | Storytelling, slides e ensaio da apresentação |

## Distribuição
Must: 12 itens (54 pts) · Should: 6 itens (25 pts) · Could: 3 itens (10 pts) · Won't: 2 itens.

## Análise exploratória das prioridades

A simulação com o perfil de professor da área de TI sugere três frentes prioritárias para o Sistema de Apoio ao ENADE:

**1. Banco de questões**

Centralizar provas e questões do ENADE, permitindo consultas por curso, ano e componente.

**2. Simulados**

Permitir que os estudantes realizem simulados e consultem resultados detalhados para identificar dificuldades.

**3. Acompanhamento do desempenho**

Disponibilizar estatísticas individuais e informações agregadas que apoiem o acompanhamento pedagógico.

Essas funcionalidades são candidatas à prioridade Must no método MoSCoW, sujeitas à validação com stakeholders e à revisão das prioridades existentes.

Funcionalidades complementares, como fórum e notificações, podem ser consideradas para etapas posteriores, de acordo com o escopo aprovado pelo grupo.

Esta análise se baseia em uma simulação exploratória e não representa uma priorização validada por um entrevistado real.