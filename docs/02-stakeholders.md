# 2. Identificação de Stakeholders

## 2.1 Lista de stakeholders
| ID | Stakeholder | Tipo | Papel / interesse | Expectativas principais | Influência | Interesse |
|----|-------------|------|-------------------|-------------------------|-----------|-----------|
| SH01 | Estudantes concluintes | Usuário primário | Preparar-se para o ENADE | Questões organizadas, simulados, feedback, facilidade de uso | Média | Alto |
| SH02 | Estudantes de outros semestres | Usuário secundário | Prática antecipada | Acesso ao banco e ao fórum | Baixa | Médio |
| SH03 | Professores | Usuário / colaborador | Comentar questões e apoiar pedagogicamente | Ferramenta simples para comentar e responder dúvidas | Média | Médio |
| SH04 | Coordenações de curso | Cliente / patrocinador interno | Acompanhar desempenho dos cursos | Relatórios agregados, indicadores por área | Alta | Alto |
| SH05 | Administradores do sistema | Usuário operacional | Gerir questões, usuários e moderação | Painel administrativo, controle de conteúdo | Alta | Alto |
| SH06 | Instituição (Unifor) / NDE | Patrocinador | Melhorar indicadores de qualidade | Aderência institucional, impacto no desempenho | Alta | Médio |
| SH07 | INEP | Fonte externa | Publica as provas e microdados | Respeito aos termos de uso do conteúdo | Alta (externa) | Baixo |
| SH08 | Equipe do projeto (Grupo 1) | Desenvolvedor / analista | Especificar o sistema | Requisitos claros e viáveis | Alta | Alto |
| SH09 | Professor da disciplina | Avaliador | Avaliar o trabalho | Aderência à engenharia de requisitos | Alta | Alto |
| SH10 | Equipe de TI da instituição | Apoio técnico | Hospedagem e segurança | Conformidade com políticas e LGPD | Média | Baixo |

## 2.2 Matriz Poder × Interesse
| | **Interesse baixo** | **Interesse alto** |
|---|---|---|
| **Poder alto** | Manter satisfeitos: SH07 (INEP), SH10 (TI), SH06 (instituição) | **Gerenciar de perto:** SH04 (coordenações), SH05 (administradores), SH08, SH09 |
| **Poder baixo** | Monitorar: SH02 | **Manter informados:** SH01 (estudantes), SH03 (professores) |

## 2.3 Plano de engajamento
| Stakeholder | Técnica de elicitação | Frequência |
|-------------|-----------------------|-----------|
| SH01/SH02 | Entrevistas e formulário online | Sprint 1; validação na Sprint 2 |
| SH03 | Entrevista | Sprint 1 |
| SH04 | Entrevista semiestruturada | Sprint 1; validação final |
| SH05 | Entrevista sobre rotinas administrativas | Sprint 1 |
| SH09 | Revisões e feedback do trabalho | A cada entrega |

## 2.4 Personas
**Ana, 22 anos — estudante concluinte de Sistemas de Informação.** Concilia estágio e faculdade; estuda à noite pelo celular; não sabe onde achar questões do seu curso; quer saber em que áreas está mais fraca.

**Prof. Carlos, 45 anos — professor e membro do NDE.** Tem pouco tempo; quer comentar questões de forma simples e entender as dúvidas mais frequentes.

**Marina, 38 anos — coordenadora de curso.** Precisa de indicadores agregados para planejar reforço pedagógico antes do exame.
