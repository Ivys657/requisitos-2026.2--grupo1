# 7. Modelagem UML

> Os diagramas abaixo usam **Mermaid** e renderizam automaticamente no GitHub. Os arquivos-fonte ficam em `docs/diagramas/`. Para o PDF ou apresentação, podem ser redesenhados no Draw.io, Lucidchart ou Astah seguindo a mesma estrutura.

## 7.1 Diagrama de Casos de Uso

### Atores
| Ator | Descrição |
|------|-----------|
| Estudante | Usuário que estuda, responde questões, faz simulados e participa do fórum |
| Professor | Comenta questões e apoia pedagogicamente |
| Coordenador | Acompanha desempenho agregado do curso |
| Administrador | Gerencia questões, usuários e moderação |

### Casos de uso
| ID | Caso de uso | Ator(es) | Requisitos |
|----|-------------|----------|-----------|
| UC01 | Cadastrar-se | Estudante | RF01 |
| UC02 | Autenticar-se | Todos | RF02, RF04 |
| UC03 | Consultar e filtrar questões | Estudante | RF05, RF06 |
| UC04 | Responder questão | Estudante | RF07 |
| UC05 | Realizar simulado cronometrado | Estudante | RF12–RF15 |
| UC06 | Ver gabarito comentado | Estudante | RF10 |
| UC07 | Ver estatísticas de desempenho | Estudante | RF16, RF17 |
| UC08 | Participar do fórum da questão | Estudante, Professor | RF19, RF20, RF22 |
| UC09 | Recuperar senha | Todos | RF03 |
| UC10 | Gerenciar questões | Administrador | RF09 |
| UC11 | Comentar questão | Professor | RF11 |
| UC12 | Acompanhar desempenho agregado | Coordenador | RF18 |
| UC13 | Moderar fórum | Administrador | RF21 |
| UC14 | Gerenciar usuários | Administrador | RF23 |

```mermaid
flowchart LR
    EST([Estudante])
    PRO([Professor])
    COO([Coordenador])
    ADM([Administrador])

    subgraph SIS[Sistema ENADE Prep]
        UC01((UC01 Cadastrar-se))
        UC02((UC02 Autenticar-se))
        UC09((UC09 Recuperar senha))
        UC03((UC03 Consultar e filtrar questões))
        UC04((UC04 Responder questão))
        UC05((UC05 Realizar simulado cronometrado))
        UC06((UC06 Ver gabarito comentado))
        UC07((UC07 Ver estatísticas))
        UC08((UC08 Participar do fórum))
        UC10((UC10 Gerenciar questões))
        UC11((UC11 Comentar questão))
        UC12((UC12 Acompanhar desempenho agregado))
        UC13((UC13 Moderar fórum))
        UC14((UC14 Gerenciar usuários))
    end

    EST --- UC01
    EST --- UC02
    EST --- UC03
    EST --- UC04
    EST --- UC05
    EST --- UC06
    EST --- UC07
    EST --- UC08
    PRO --- UC02
    PRO --- UC11
    PRO --- UC08
    COO --- UC02
    COO --- UC12
    ADM --- UC02
    ADM --- UC10
    ADM --- UC13
    ADM --- UC14

    UC02 -. "«extend»" .-> UC09
    UC04 -. "«include»" .-> UC06
    UC05 -. "«include»" .-> UC06
    UC03 -. "«include»" .-> UC02
```

### Especificação resumida — UC05 Realizar simulado cronometrado
| Campo | Descrição |
|-------|-----------|
| Ator principal | Estudante |
| Pré-condição | Estudante autenticado |
| Fluxo principal | 1. Estudante escolhe curso, componente e quantidade de questões. 2. Sistema gera o simulado e inicia o cronômetro. 3. Estudante responde as questões. 4. Sistema salva cada resposta automaticamente. 5. Estudante finaliza ou o tempo se esgota. 6. Sistema calcula a nota e exibe resultado e revisão (UC06). |
| Fluxos alternativos | A1. Conexão cai → sistema permite retomar em até 30 min (RN18). A2. Tempo esgota → encerramento automático (RN07). |
| Pós-condição | Resultado registrado nas estatísticas do estudante |
| Regras | RN07, RN08, RN09, RN18 |

## 7.2 Diagrama de Componentes

```mermaid
flowchart TB
    subgraph CLI[Camada de Apresentação]
        WEB[Aplicação Web Responsiva]
        MOB[Interface Mobile / PWA]
    end

    GW[API Gateway / Back-end API REST]

    subgraph APP[Camada de Aplicação - Módulos]
        AUTH[Módulo de Autenticação e Perfis]
        QST[Módulo de Questões]
        SIM[Módulo de Simulados]
        GAB[Módulo de Gabarito Comentado]
        EST[Módulo de Estatísticas]
        FOR[Módulo de Fórum e Moderação]
        ADM[Módulo de Administração]
        NOT[Serviço de Notificações]
    end

    subgraph DAD[Camada de Dados]
        DB[(Banco de Dados Relacional)]
        CCH[(Cache)]
        FS[(Armazenamento de Arquivos)]
    end

    subgraph EXT[Serviços Externos]
        MAIL[Serviço de E-mail]
        INEP[Portal INEP - provas oficiais]
    end

    WEB -->|HTTPS/JSON| GW
    MOB -->|HTTPS/JSON| GW
    GW --> AUTH
    GW --> QST
    GW --> SIM
    GW --> GAB
    GW --> EST
    GW --> FOR
    GW --> ADM
    SIM --> QST
    SIM --> EST
    GAB --> QST
    FOR --> QST
    FOR --> NOT
    ADM --> QST
    AUTH --> DB
    QST --> DB
    SIM --> DB
    SIM --> CCH
    GAB --> DB
    EST --> DB
    FOR --> DB
    ADM --> DB
    QST --> FS
    NOT --> MAIL
    AUTH --> MAIL
    ADM -.->|importação manual de provas| INEP
```

| Componente | Responsabilidade | Requisitos |
|-----------|------------------|-----------|
| Autenticação e Perfis | Cadastro, login, recuperação de senha, controle de acesso | RF01–RF04 |
| Questões | Banco, busca e filtros, resposta | RF05–RF08 |
| Simulados | Geração, cronômetro, correção | RF12–RF15 |
| Gabarito Comentado | Gabarito oficial e explicações | RF10, RF11 |
| Estatísticas | Desempenho individual e agregado | RF16–RF18 |
| Fórum e Moderação | Tópicos, respostas, denúncias | RF19–RF22 |
| Administração | Gestão de questões e usuários | RF09, RF23, RF24 |
| Notificações | E-mails e avisos | RF03, RF22 |

## 7.3 Diagrama de Implantação

```mermaid
flowchart TB
    subgraph CD[Dispositivo do Usuário]
        BR[Navegador Web / Mobile<br/>«execution environment»]
    end

    subgraph CLOUD[Infraestrutura em Nuvem]
        LB[Load Balancer + TLS<br/>«node»]
        subgraph APPN[Servidor de Aplicação - Containers]
            FE[Front-end estático<br/>«artifact»]
            API[API Back-end<br/>«artifact»]
        end
        subgraph DBN[Servidor de Banco de Dados]
            PG[(Banco Relacional<br/>«artifact»)]
        end
        CA[(Servidor de Cache<br/>«node»)]
        ST[Armazenamento de Objetos<br/>«node»]
        BK[Backup diário<br/>«node»]
    end

    SMTP[Servidor de E-mail<br/>«external»]

    BR -->|HTTPS 443| LB
    LB --> FE
    LB --> API
    API -->|TCP| PG
    API -->|TCP| CA
    API -->|HTTPS| ST
    API -->|SMTP/API| SMTP
    PG --> BK
```

| Nó | Tecnologia sugerida (referência) | Observação |
|----|----------------------------------|-----------|
| Navegador / Mobile | Chrome, Firefox, Edge, Safari | Web responsiva (RNF03, RNF13) |
| Load Balancer | Nginx ou balanceador do provedor | TLS (RNF06) |
| API Back-end | Container (ex.: Node.js ou Java) | Stateless, escalável (RNF02) |
| Banco relacional | PostgreSQL | Backup diário (RNF10) |
| Cache | Redis | Estado dos simulados em andamento (RNF11) |

> As tecnologias são sugestões para fundamentar a implantação; o projeto é conceitual e não implementa código.
