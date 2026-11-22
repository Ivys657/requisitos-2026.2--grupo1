# Documento de Especificação de Requisitos de Software (SRS)
**Projeto:** Sistema de Apoio ao ENADE

**Entrega:** Atividade 2 — P2 / Sprint 2 (M2)

**Referência de estrutura:** IEEE 830 (organização adaptada ao enunciado da disciplina)

**Versão:** 0.2 — revisão para validação pela equipe

**Estado:** especificação e prototipagem; o sistema não está implementado

## 1. Introdução
### 1.1 Objetivo do documento
Especificar funções, restrições, regras de negócio e comportamentos esperados do Sistema de Apoio ao ENADE. O documento liga necessidades identificadas ou propostas, requisitos funcionais e não funcionais, regras de negócio, diagramas UML e especificações de casos de uso. Serve de base para a revisão de consistência e para os protótipos navegáveis da Sprint 2.

### 1.2 Escopo do produto
Plataforma web **proposta** para apoiar a preparação de estudantes para o ENADE, reunindo questões, resolução individual, simulados cronometrados, gabaritos comentados e acompanhamento do desempenho. Professores poderão complementar questões com comentários pedagógicos; coordenadores poderão consultar indicadores agregados de seus cursos; administradores poderão gerir questões, usuários e conteúdo do fórum.

Nesta entrega, são produzidas **especificações e interfaces de demonstração**, não a implementação de um sistema de produção.

### 1.3 Termos e siglas
| Sigla | Significado |
|---|---|
| ENADE | Exame Nacional de Desempenho dos Estudantes |
| RF | Requisito funcional |
| RNF | Requisito não funcional |
| RN | Regra de negócio |
| UC | Caso de uso |
| SRS | Software Requirements Specification |
| Nxx | Necessidade formalizada no projeto |
| Hxx | Hipótese de necessidade da entrevista simulada |
| P1 / P2 | Etapas avaliativas da disciplina |

### 1.4 Documentos de referência
- [`01-documento-de-visao.md`](01-documento-de-visao.md)

- [`02-stakeholders.md`](02-stakeholders.md)

- [`03-entrevistas.md`](03-entrevistas.md) — inclui **entrevista simulada**, não entrevista com stakeholder real

- [`04-requisitos.md`](04-requisitos.md)

- [`05-regras-de-negocio.md`](05-regras-de-negocio.md)

- [`06-backlog-priorizado.md`](06-backlog-priorizado.md)

- [`07-uml.md`](07-uml.md) e [`diagramas/`](diagramas/)

- [`09-revisao-consistencia.md`](09-revisao-consistencia.md)

## 2. Descrição geral
### 2.1 Perspectiva
Aplicação web planejada para desktop e dispositivos móveis. Protótipos podem simular os fluxos, mas não equivalem a autenticação real, banco de dados, envio de e-mails ou cálculo persistente de resultados.

### 2.2 Perfis de usuários
| Perfil | Responsabilidade principal |
|---|---|
| Estudante | Consultar e responder questões; realizar simulados; acompanhar desempenho; participar do fórum |
| Professor | Inserir ou editar comentários pedagógicos em questões, conforme autorização; participar do fórum |
| Coordenador | Consultar resultados agregados e anonimizados do curso autorizado |
| Administrador | Gerenciar questões, usuários e moderação do fórum |

A regra **RN01** estabelece um único perfil principal por usuário. O administrador exerce as funções de moderação previstas no modelo atual; não se pressupõe um quinto perfil independente.

### 2.3 Funções principais
Cadastro e autenticação; banco de questões; respostas e gabaritos; simulados; desempenho; fórum; administração.

### 2.4 Ambiente operacional
Navegadores atuais em computadores e dispositivos móveis, de acordo com RNF03 e RNF13. A infraestrutura concreta do produto não está implementada nesta etapa.

### 2.5 Premissas, dependências e limites
- As necessidades derivadas da **entrevista simulada** são hipóteses, não evidências de entrevista real.

- As funcionalidades propostas ou inferidas precisam ser explicitadas e validadas para evitar **gold plating**.

- A hierarquia **curso → disciplina → conteúdo → material/questão** foi sugerida como hipótese de modelagem pelo professor, mas **não está aprovada como requisito**.

- As restrições de privacidade, permissão, tempo e persistência devem obedecer às regras RN01–RN18.

- Valores ou comportamentos não definidos (por exemplo, duração do bloqueio de login) não devem ser apresentados como regras já aprovadas.

## 3. Requisitos específicos
### 3.1 Requisitos funcionais
A relação abaixo resume os requisitos da P1. A redação integral, prioridade e origem devem permanecer em [`04-requisitos.md`](04-requisitos.md).

| ID | Requisito resumido |
|---|---|
| RF01 | Cadastrar estudantes com nome, e-mail, curso e senha |
| RF02 | Autenticar estudantes, professores, coordenadores e administradores |
| RF03 | Recuperar senha por e-mail |
| RF04 | Aplicar controle de acesso por perfil |
| RF05 | Exibir questões organizadas por ano, curso/área e componente |
| RF06 | Buscar e filtrar questões por ano, curso, componente e palavra-chave |
| RF07 | Responder questão individualmente e receber resultado imediato |
| RF08 | Favoritar questões e marcá-las para revisão |
| RF09 | Administrar questões: cadastrar, editar, desativar e importar |
| RF10 | Exibir gabarito e explicação após resposta ou finalização do simulado |
| RF11 | Permitir que professores autorizados cadastrem ou editem comentários pedagógicos |
| RF12 | Gerar simulado por curso, componente e quantidade de questões |
| RF13 | Cronometrar o simulado e encerrar ao fim do tempo |
| RF14 | Retomar simulado após queda de conexão dentro da tolerância definida |
| RF15 | Exibir nota, acertos por área e revisão de questões ao finalizar |
| RF16 | Exibir desempenho individual por área em gráficos |
| RF17 | Exibir evolução do desempenho ao longo do tempo |
| RF18 | Exibir desempenho agregado e anonimizado por curso para coordenadores |
| RF19 | Oferecer fórum por questão com tópicos e respostas |
| RF20 | Permitir denúncias de conteúdo inadequado |
| RF21 | Permitir que administradores ocultem ou removam conteúdo |
| RF22 | Notificar respostas a tópicos do usuário |
| RF23 | Administrar contas: ativar, desativar e alterar perfil |
| RF24 | Consultar indicadores administrativos de uso |

### 3.2 Requisitos não funcionais
| ID | Critério existente na P1 |
|---|---|
| RNF01 | Telas principais carregam em até 3 s com 4G (P95) |
| RNF02 | Suporte a 500 usuários simultâneos |
| RNF03 | Interface responsiva a partir de 360 px |
| RNF04 | Novo usuário inicia um simulado em até 5 cliques |
| RNF05 | Acessibilidade WCAG 2.1 nível AA |
| RNF06 | Senhas com hash e salt; comunicação HTTPS/TLS |
| RNF07 | Sessões expiram e há proteção contra ataques comuns |
| RNF08 | Privacidade e tratamento de dados conforme LGPD |
| RNF09 | Disponibilidade mínima de 99% |
| RNF10 | Backup diário e retenção de 30 dias |
| RNF11 | Respostas do simulado são salvas a cada questão |
| RNF12 | Arquitetura modular e documentada |
| RNF13 | Chrome, Firefox, Edge e Safari atuais; web em Android/iOS |
| RNF14 | Busca escalável com mais de 10.000 questões |
| RNF15 | Respeito aos termos de uso das provas publicadas pelo INEP |

**Observação de verificação:** critérios de desempenho, disponibilidade, segurança e backup são requisitos do produto futuro; **não podem ser comprovados apenas por protótipos no Stitch**. Nesta P2, a revisão deve distinguir verificações por inspeção do protótipo das que dependerão de implementação e testes.

### 3.3 Especificação de casos de uso
Cada arquivo associado detalha ator, objetivo, pré-condições, pós-condições, campos de entrada e saída, fluxo principal, alternativas, exceções e regras aplicáveis. O nome e a numeração originais da P1 são preservados.

| UC | Operação | Requisitos vinculados | Regras de negócio relevantes | Documento |
|---|---|---|---|---|
| UC01 | Cadastrar-se | RF01 | RN01, RN02, RN16 | [UC01](casos-de-uso/UC01.md) |
| UC02 | Autenticar-se | RF02, RF04 | RN01, RN15 | [UC02](casos-de-uso/UC02.md) |
| UC03 | Consultar e filtrar questões | RF05, RF06 | RN04, RN05, RN17 | [UC03](casos-de-uso/UC03.md) |
| UC04 | Responder questão | RF07; RF08 **pendente de detalhamento** | RN06 | [UC04](casos-de-uso/UC04.md) |
| UC05 | Realizar simulado cronometrado | RF12–RF15 | RN05, RN06, RN07, RN08, RN09, RN18 | [UC05](casos-de-uso/UC05.md) |
| UC06 | Ver gabarito comentado | RF10 | RN06, RN17 | [UC06](casos-de-uso/UC06.md) |
| UC07 | Ver estatísticas de desempenho | RF16, RF17 | RN10 | [UC07](casos-de-uso/UC07.md) |
| UC08 | Participar do fórum da questão | RF19, RF20, RF22 | RN12, RN13 | [UC08](casos-de-uso/UC08.md) |
| UC09 | Recuperar senha | RF03 | RN15 (segurança de acesso, quando aplicável) | [UC09](casos-de-uso/UC09.md) |
| UC10 | Gerenciar questões | RF09 | RN03, RN04, RN05, RN17 | [UC10](casos-de-uso/UC10.md) |
| UC11 | Comentar questão | RF11 | RN06, RN14 | [UC11](casos-de-uso/UC11.md) |
| UC12 | Acompanhar desempenho agregado | RF18 | RN11 | [UC12](casos-de-uso/UC12.md) |
| UC13 | Moderar fórum | RF21; RF20 como origem de denúncia | RN12, RN13 | [UC13](casos-de-uso/UC13.md) |
| UC14 | Gerenciar usuários | RF23, RF04 | RN01, RN16 | [UC14](casos-de-uso/UC14.md) |

**Cobertura pendente:** RF08 (favoritos/revisão) precisa ser incluído explicitamente em UC04 ou receber caso próprio; RF24 (indicadores de administração) não possui caso de uso dedicado. A equipe deve decidir se acrescenta caso de uso (ex.: UC15, **somente se aprovado**) e atualiza [`07-uml.md`](07-uml.md). RF20 e RF22 já aparecem vinculados a UC08, mas exigem fluxos completos e verificáveis.

### 3.4 Regras transversais de validação
As 18 regras completas estão em [`05-regras-de-negocio.md`](05-regras-de-negocio.md). Na revisão dos casos, observar especialmente:

- **RN02 — e-mail único:** UC01 deve rejeitar duplicidade sem criar outra conta.

- **RN05 — questões desativadas:** UC03 e novos simulados não as exibem; históricos existentes são preservados.

- **RN06 — liberação do gabarito:** só após responder a questão ou concluir o simulado.

- **RN07–RN09 — simulado:** encerramento ao fim do tempo, questões sem marcação incorretas, peso igual por questão e seleção restrita ao curso/área, exceto formação geral.

- **RN10 — desempenho individual:** um estudante não acessa estatísticas de outro.

- **RN11 — agregação:** coordenador vê apenas dados anonimizados do seu curso e agrupamentos com **mínimo de cinco estudantes**.

- **RN13 — denúncias:** conteúdo denunciado por **três usuários diferentes** fica oculto até revisão da moderação.

- **RN15 — tentativas de login:** bloquear temporariamente após **cinco tentativas inválidas consecutivas**; duração do bloqueio a definir.

- **RN18 — retomada:** permitir retomada até **30 minutos** após queda de conexão, sem alterar o tempo restante, conforme regra atual; comportamento do cronômetro durante a interrupção deve ser esclarecido na especificação.

### 3.5 Interfaces externas e fluxos de navegação para o protótipo
A prototipagem deve representar as transições entre as telas, com dados fictícios, sem sugerir processamento real. Fluxos recomendados:

1. **Acesso:** Login → Cadastro → Confirmação / Recuperação de senha → Login → Painel do perfil.

2. **Questões:** Painel do estudante → Banco de questões → Filtros → Questão → Responder → Resultado → Gabarito comentado.

3. **Simulado:** Painel do estudante → Configuração → Execução cronometrada → Encerramento → Resultado → Revisão.

4. **Desempenho e fórum:** Painel → Gráficos / Histórico; Questão → Tópicos → Resposta / Denúncia.

5. **Perfis institucionais:** Professor → Comentários; Coordenador → Painel agregado; Administrador → Questões / Usuários / Moderação.

**Elementos de interface a verificar:** mensagens de campos obrigatórios, e-mail duplicado, credenciais inválidas, bloqueio após cinco tentativas, nenhuma questão encontrada, tempo esgotado, simulado interrompido, gabarito indisponível antes da resposta, ausência de dados e resultados agregados com menos de cinco estudantes.

### 3.6 Rastreabilidade e critérios de aceite
O encadeamento esperado é **necessidade → RF → UC → regra aplicável → tela/fluxo → evidência de revisão**. A matriz de necessidades e requisitos fica em [`04-requisitos.md`](04-requisitos.md), e a verificação cruzada no relatório [`09-revisao-consistencia.md`](09-revisao-consistencia.md).

Exemplos de critérios de aceite para inspeção do protótipo:

| UC | Critério de aceite visual/navegacional |
|---|---|
| UC01 | Cadastro mostra campos obrigatórios e estado de e-mail já cadastrado |
| UC02 | Login prevê erros e estado de bloqueio após cinco falhas |
| UC03 | Filtros produzem lista e estado vazio; itens desativados não são exibidos |
| UC05 | Simulado prevê configuração, cronômetro, encerramento, revisão e cenário de retomada |
| UC08 | Fórum prevê criação de tópico, resposta, denúncia e estado de ocultação |
| UC12 | Painel do coordenador não exibe dados individuais nem agrupamentos com menos de cinco estudantes |

Esses são critérios de **inspeção do protótipo**, não prova de conformidade do software em produção.

## 4. Revisão de consistência e pendências
Consultar também [`09-revisao-consistencia.md`](09-revisao-consistencia.md).

| ID | Ponto a conferir | Encaminhamento |
|---|---|---|
| PC01 | Necessidades ainda não validadas e matriz incompleta na `main` | Confirmar origem e rastrear todos os RFs sem apresentar hipótese como entrevista real |
| PC02 | RF08 sem ação explícita no UC04 | Especificar fluxo de favoritar/revisar ou aprovar novo caso de uso |
| PC03 | RF20 e RF22 citados no UC08, mas sem fluxo detalhado | Modelar denúncia, ocultação e notificação como eventos/fluxos |
| PC04 | RF24 sem UC explícito | Definir caso de uso ou ajustar escopo e UML, mediante revisão do grupo |
| PC05 | Relação curso → disciplina → conteúdo → material/questão não aprovada | Não fixar hierarquia nova na interface sem validação |
| PC06 | RN15 não especifica duração do bloqueio | Deixar prazo como decisão pendente |
| PC07 | RN18 e RN07 exigem definição clara sobre passagem do tempo na desconexão | Esclarecer comportamento sem alterar regra aprovada de retomada |
| PC08 | Diagrama de casos de uso e especificações separados | Conferir coerência de atores, nomenclatura e relacionamentos em `07-uml.md` |
| PC09 | RNF não verificáveis pelo protótipo | Marcar verificações técnicas como futuras, sem alegar testes executados |
| PC10 | Protótipo navegável e sua publicação | Registrar link e testar caminhos; atualizar README e AVA |

## 5. Aprovação e histórico
**Situação:** documento de trabalho revisado, ainda **pendente de conferência com os artefatos da P1, validação pela equipe e aprovação acadêmica**.

| Versão | Alteração |
|---|---|
| 0.1 | Esqueleto inicial do SRS para Sprint 2 |
| 0.2 | Rastreabilidade UC–RF–RN, pontos de validação, critérios para prototipagem e pendências explícitas |
