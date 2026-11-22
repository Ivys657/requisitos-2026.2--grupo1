# Revisão de consistência — Sprint 2 (atualização após especificar UCs)

> Documento de trabalho. **“Especificado” não significa implementado ou validado.** Compare com `07-uml.md` atual antes do merge.

| Verificação | Resultado desta revisão | Próxima ação |
|---|---|---|
| UC01–UC14 | 14 arquivos com atores, entradas, saídas, fluxos, alternativas e critérios visuais | Revisão da equipe e conferência com `07-uml.md` |
| RF08 | Fluxo Favoritar/Marcar revisão detalhado em UC04 | Aprovar representação em `07-uml.md` |
| RF20 | Denunciar e contabilizar denunciantes diferentes detalhado em UC08 | Revisar UC08/UC13 e protótipo |
| RF22 | Geração de notificação após resposta detalhada em UC08 | Validar canal final de notificação |
| RF24 | Sem UC original; `docs/propostas/UC15-PROPOSTA-indicadores-admin.md` é só proposta | Aprovar UC15 e atualizar UML/SRS OU retirar RF24 do escopo da iteração |
| RN15 | UC02 apresenta 5 falhas e bloqueio temporário | Determinar duração com stakeholder; não inventar valor |
| RN18 × RN07 | UC05 apresenta 30 min de tolerância e aviso de desconexão | Definir política de cronômetro offline; não implementar regra imaginada |
| RN11 | UC12 proíbe exibir grupos com <5 estudantes | Testar tela de dados insuficientes |
| RN13 | UC08/UC13 descrevem ocultação após denúncias de 3 usuários diferentes | Testar cenário de ocultação/moderação |
| Questões desligadas | UC03/UC10 aplicam RN05; histórico permanece | Conferir telas e diagramas |
| Necessidade → RF | Versão completa do `04-requisitos.md` pode não ter chegado à `main` | Conferir arquivo atual do repositório e integrar somente depois de revisão |
| UML | Nome e numeração originais UC01–UC14 preservados | Conferir modelo da `main` e atualizar relacionamentos pendentes |
| SRS | SRS v0.2 existente pode precisar refletir o detalhamento de RF08/RF20/RF22 e decisão RF24 | Atualizar texto pontualmente, sem reformatar tudo |
| Protótipo | Prompt e mapa de telas preparados | Gerar no Stitch, conectar telas e inspecionar navegação |

## Critérios de aceitação da Sprint 2

- [ ] Equipe revisou 14 especificações de UC e as regras RN01–RN18.
- [ ] Escopo RF08/RF20/RF22 definido e representado na documentação.
- [ ] RF24 decidido pelo grupo (UC15 opcional ou ajuste do escopo da iteração).
- [ ] `07-uml.md` e seu diagrama atualizados se necessário.
- [ ] SRS coerente com as especificações finalizadas.
- [ ] Protótipo Stitch acessível, com fluxo de cadastro, questões, simulado e moderação.
- [ ] Estados de erro e privacidade testados visualmente.
- [ ] Link do protótipo no README e evidências no GitHub/AVA.
- [ ] Pull Request revisada e integrada pela equipe.
