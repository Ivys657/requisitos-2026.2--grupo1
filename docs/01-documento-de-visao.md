# 1. Documento de Visão — Sistema de Apoio ao ENADE

## 1.1 Introdução
Este documento define a visão do produto **ENADE Prep** (nome provisório): uma plataforma web/mobile de questões comentadas do ENADE, com simulados cronometrados, estatísticas de desempenho e fórum colaborativo.

## 1.2 Contexto e descrição do problema
O ENADE é componente curricular obrigatório e indicador fundamental da qualidade do ensino superior brasileiro. Apesar disso, os estudantes enfrentam dificuldades no preparo.

| Item | Descrição |
|------|-----------|
| **O problema** | Falta de materiais organizados, de simulados práticos e de feedback sobre o desempenho na preparação para o ENADE |
| **Afeta** | Estudantes de graduação concluintes, coordenações de curso e professores |
| **Impacto** | Baixo engajamento com a prova, preparo desigual entre cursos e pouca visibilidade do desempenho por área de conhecimento |
| **Solução bem-sucedida** | Plataforma única, organizada por ano/curso/componente, com prática realista e feedback mensurável |

As questões do ENADE são públicas (portal do INEP), porém dispersas em PDFs, sem comentários, filtros ou métricas.

## 1.3 Sentença de posicionamento do produto
**Para** estudantes de graduação que realizarão o ENADE, **que** precisam se preparar com material organizado e feedback, **o** ENADE Prep **é uma** plataforma web/mobile de questões comentadas **que** oferece banco de questões filtrável, simulados cronometrados, gabaritos comentados e estatísticas de desempenho. **Diferentemente de** plataformas genéricas de concursos (ex.: QConcursos, Estuda.com), **nosso produto** é focado no ENADE, integrado ao contexto universitário e com visão para coordenações e professores.

## 1.4 Objetivos do produto
1. Centralizar as questões do ENADE organizadas por ano, curso/área e componente (formação geral e conhecimento específico).
2. Permitir prática realista por meio de simulados cronometrados.
3. Fornecer gabarito comentado para compreensão dos conceitos.
4. Oferecer estatísticas de desempenho por área de conhecimento.
5. Promover aprendizado colaborativo via fórum por questão.
6. Apoiar coordenações e professores no acompanhamento do desempenho.

## 1.5 Escopo
**Dentro do escopo (versão inicial)**
- Banco de questões · Simulados cronometrados · Gabarito comentado · Estatísticas de desempenho · Fórum de discussão · Cadastro e autenticação (estudantes e administradores).

**Fora do escopo (nesta fase)**
- Implementação de código (projeto conceitual).
- Correção oficial/emissão de nota do ENADE (o sistema não substitui a prova oficial).
- Integração com sistemas acadêmicos institucionais (candidata a versões futuras).
- Aplicativos nativos separados (adotar web responsiva/PWA ou mobile como visão futura).

## 1.6 Usuários e partes interessadas (resumo)
| Perfil | Necessidade principal |
|--------|----------------------|
| Estudante | Estudar com questões organizadas, simular a prova e acompanhar evolução |
| Professor | Contribuir com comentários e apoiar pedagogicamente |
| Coordenação de curso | Acompanhar desempenho agregado dos estudantes |
| Administrador | Manter questões, usuários e moderação |

Detalhamento em [02-stakeholders.md](02-stakeholders.md).

## 1.7 Principais necessidades e funcionalidades de alto nível
| Necessidade | Funcionalidade |
|-------------|----------------|
| Material organizado | Banco de questões com filtros (ano, curso, componente) |
| Prática realista | Simulados com cronômetro |
| Compreensão dos conceitos | Gabarito comentado |
| Feedback sobre desempenho | Painel de estatísticas com gráficos |
| Aprendizado colaborativo | Fórum por questão |
| Acesso seguro | Cadastro e autenticação por perfil |

## 1.8 Restrições, premissas e dependências
- **Restrições:** projeto conceitual; ferramentas gratuitas; requisitos realistas e factíveis; documentação em padrão profissional (IEEE 830).
- **Premissas:** questões do ENADE estão disponíveis publicamente no portal do INEP; estudantes têm acesso a internet.
- **Dependências:** disponibilidade e licenciamento de uso das provas do INEP; professores voluntários para comentar questões.

## 1.9 Riscos iniciais
| Risco | Prob. | Impacto | Mitigação |
|-------|-------|---------|-----------|
| Questões sem comentários suficientes | Alta | Alto | Parceria com professores; comentários colaborativos moderados |
| Baixa adesão dos estudantes | Média | Alto | Gamificação leve, divulgação pela coordenação |
| Conteúdo inadequado no fórum | Média | Médio | Moderação e denúncia de conteúdo |
| Requisitos mal compreendidos | Média | Alto | Entrevistas, validação com stakeholders |

## 1.10 Critérios de sucesso
- ≥ 80% dos entrevistados validam a priorização dos requisitos *Must*.
- Todos os entregáveis da Sprint 1 versionados no repositório.
- Modelos UML consistentes com os requisitos especificados.

## 1.11 Impacto social esperado
Democratização do acesso a materiais de qualidade, melhoria do desempenho dos estudantes, fortalecimento da relação universidade-comunidade e desenvolvimento de habilidades técnicas e sociais.
