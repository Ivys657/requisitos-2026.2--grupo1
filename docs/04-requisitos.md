# 4. Requisitos do Sistema

**Prioridade (MoSCoW):** M = Must · S = Should · C = Could · W = Won't (nesta versão)
**Origem:** E = entrevistas · B = benchmark · P = proposta do projeto

## 4.1 Requisitos Funcionais

### Autenticação e Contas
| ID | Requisito | Prior. | Origem |
|----|-----------|--------|--------|
| RF01 | O sistema deve permitir o cadastro de estudantes com nome, e-mail, curso e senha | M | P |
| RF02 | O sistema deve autenticar usuários (estudante, professor, coordenador, administrador) por e-mail e senha | M | P |
| RF03 | O sistema deve permitir a recuperação de senha por e-mail | S | E |
| RF04 | O sistema deve aplicar controle de acesso por perfil | M | P |

### Banco de Questões
| ID | Requisito | Prior. | Origem |
|----|-----------|--------|--------|
| RF05 | O sistema deve exibir questões organizadas por ano, curso/área de conhecimento e componente (formação geral / conhecimento específico) | M | P |
| RF06 | O sistema deve permitir buscar e filtrar questões por ano, curso, componente e palavra-chave | M | E |
| RF07 | O estudante deve poder responder uma questão e receber o resultado imediato | M | E |
| RF08 | O estudante deve poder favoritar e marcar questões para revisão | C | E |
| RF09 | O administrador deve poder cadastrar, editar, desativar e importar questões | M | P |

### Gabarito Comentado
| ID | Requisito | Prior. | Origem |
|----|-----------|--------|--------|
| RF10 | O sistema deve exibir o gabarito oficial e a explicação detalhada de cada questão após a resposta | M | P |
| RF11 | Professores devem poder cadastrar e editar comentários nas questões | S | E |

### Simulados
| ID | Requisito | Prior. | Origem |
|----|-----------|--------|--------|
| RF12 | O estudante deve poder gerar um simulado configurando curso, componente e quantidade de questões | M | P |
| RF13 | O sistema deve cronometrar o simulado e encerrá-lo automaticamente ao fim do tempo | M | P |
| RF14 | O sistema deve permitir pausar/retomar o simulado em caso de queda de conexão, dentro de uma tolerância | S | E |
| RF15 | Ao final, o sistema deve exibir nota, acertos por área e revisão das questões | M | P |

### Estatísticas
| ID | Requisito | Prior. | Origem |
|----|-----------|--------|--------|
| RF16 | O sistema deve exibir ao estudante seu desempenho por área de conhecimento com gráficos | M | P |
| RF17 | O sistema deve exibir a evolução do desempenho ao longo do tempo | S | E |
| RF18 | O coordenador deve visualizar desempenho agregado e anonimizado por curso | S | E |

### Fórum
| ID | Requisito | Prior. | Origem |
|----|-----------|--------|--------|
| RF19 | O sistema deve oferecer um fórum de discussão por questão (criar tópico, responder) | M | P |
| RF20 | Usuários devem poder denunciar conteúdo inadequado | S | E |
| RF21 | Administradores/moderadores devem poder ocultar ou remover conteúdo | M | P |
| RF22 | O sistema deve notificar o usuário sobre respostas aos seus tópicos | C | E |

### Administração
| ID | Requisito | Prior. | Origem |
|----|-----------|--------|--------|
| RF23 | O administrador deve gerenciar usuários (ativar, desativar, alterar perfil) | M | P |
| RF24 | O administrador deve consultar indicadores de uso da plataforma | C | P |

## 4.2 Requisitos Não Funcionais (ISO/IEC 25010)
| ID | Categoria | Requisito | Medida / critério | Prior. |
|----|-----------|-----------|-------------------|--------|
| RNF01 | Desempenho | Telas principais devem carregar em até 3 s com 4G | Tempo de carga ≤ 3 s no percentil 95 | M |
| RNF02 | Desempenho | O sistema deve suportar 500 usuários simultâneos em período de pico | Teste de carga | S |
| RNF03 | Usabilidade | A interface deve ser responsiva (desktop e mobile) | Funcional em telas ≥ 360 px | M |
| RNF04 | Usabilidade | Um novo usuário deve iniciar um simulado em até 5 cliques | Teste de usabilidade | S |
| RNF05 | Acessibilidade | Aderência às diretrizes WCAG 2.1 nível AA | Auditoria | S |
| RNF06 | Segurança | Senhas armazenadas com hash e salt; comunicação via HTTPS/TLS | Revisão de segurança | M |
| RNF07 | Segurança | Sessões com expiração e proteção contra ataques comuns (OWASP Top 10) | Checklist OWASP | M |
| RNF08 | Privacidade | Conformidade com a LGPD: consentimento, minimização e direito de exclusão | Checklist LGPD | M |
| RNF09 | Disponibilidade | Disponibilidade mínima de 99% | Monitoramento mensal | S |
| RNF10 | Confiabilidade | Backup diário dos dados com retenção de 30 dias | Rotina de backup | M |
| RNF11 | Confiabilidade | Respostas do simulado salvas automaticamente a cada questão | Teste de queda de conexão | M |
| RNF12 | Manutenibilidade | Arquitetura modular com documentação atualizada | Revisão de código | S |
| RNF13 | Portabilidade | Compatível com Chrome, Firefox, Edge e Safari atuais; Android e iOS via web | Teste cross-browser | M |
| RNF14 | Escalabilidade | Banco de questões deve crescer sem degradar a busca (> 10.000 questões) | Teste de volume | C |
| RNF15 | Legal | Respeitar os termos de uso das provas publicadas pelo INEP | Revisão jurídica | M |

## 4.3 Matriz de rastreabilidade (resumo)
| Objetivo | Requisitos | Casos de uso |
|----------|-----------|--------------|
| Banco de questões organizado | RF05, RF06, RF07, RF09 | UC03, UC04, UC10 |
| Prática realista | RF12–RF15 | UC05 |
| Compreensão dos conceitos | RF10, RF11 | UC06, UC11 |
| Feedback de desempenho | RF16–RF18 | UC07, UC12 |
| Aprendizado colaborativo | RF19–RF22 | UC08, UC13 |
| Acesso seguro | RF01–RF04, RF23 | UC01, UC02, UC14 |
## Rastreabilidade das necessidades exploratórias

A simulação de entrevista com o perfil de professor da área de TI permitiu identificar hipóteses de necessidades que podem ser relacionadas aos requisitos já definidos.

| Hipótese | Necessidade | Requisitos relacionados |
|---|---|---|
| H01 | Centralizar as questões de preparação | RF05 |
| H02 | Facilitar a localização de questões | RF06 |
| H03 | Acompanhar o desempenho dos estudantes | RF16, RF17, RF18 |
| H04 | Oferecer simulados com resultados detalhados | RF12, RF13, RF15 |
| H05 | Apresentar explicações sobre os erros | RF10, RF11 |
| H06 | Identificar conteúdos com maior dificuldade | RF16, RF18 |

**Origem das necessidades:** simulação exploratória de entrevista.

**Estado de validação:** hipóteses pendentes de confirmação com stakeholders reais.

Os requisitos relacionados já fazem parte da especificação inicial e poderão ser refinados conforme novos dados de elicitação forem coletados.