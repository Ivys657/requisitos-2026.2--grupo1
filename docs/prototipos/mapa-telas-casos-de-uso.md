# Mapa de telas → casos de uso → requisitos (Sprint 2)

> Navegação sugerida para protótipo demonstrativo no Stitch. Ações sem backend usam dados fictícios.

| Tela / estado | Casos de uso | Requisitos | Regra/observação |
|---|---|---|---|
| Login, erro e bloqueio | UC02 | RF02, RF04 | RN01; RN15: 5 falhas, prazo não definido |
| Cadastro e confirmação | UC01 | RF01 | RN02: e-mail único |
| Recuperação/redefinição | UC09 | RF03 | Sem envio real de e-mail |
| Painel do estudante | Navegação | — | Menu com atalhos para UC03/UC05/UC07/UC08 |
| Banco de questões e busca vazia | UC03 | RF05, RF06 | RN05: questões desativadas ocultas |
| Resolver / favoritar questão | UC04 | RF07, RF08 | RF08 como fluxo adicional proposto no UC04 |
| Gabarito | UC06 | RF10 | RN06: depois de resposta/conclusão |
| Configurar simulado | UC05 | RF12 | RN09: curso do estudante |
| Simulado e desconexão | UC05 | RF13, RF14 | RN07, RN18, RNF11; cronômetro offline pendente |
| Resultado/revisão do simulado | UC05, UC06 | RF15, RF10 | RN08: pesos iguais; não respondidas erradas |
| Desempenho individual | UC07 | RF16, RF17 | RN10 |
| Fórum/tópico/resposta/denúncia/notificação | UC08 | RF19, RF20, RF22 | RN12; RN13: 3 denunciantes diferentes |
| Área do professor/comentário | UC11 | RF11 | RN14 |
| Desempenho agregado/insuficiente | UC12 | RF18 | RN11: grupos com no mínimo 5 estudantes |
| Admin questões/editar/desativar/importar | UC10 | RF09 | RN03–RN05, RN17 |
| Admin moderação | UC13 | RF21 | RN13 |
| Admin usuários | UC14 | RF23, RF04 | RN01 |
| Admin indicadores de uso (opcional) | UC15 PROPOSTO | RF24 | Não incorporar como aprovado sem revisão |

## Fluxos navegáveis mínimos

1. **Acesso:** Login → Cadastro → Confirmação → Login → Painel do estudante.
2. **Questões:** Painel → Banco de questões → Filtro → Questão → Responder → Gabarito → Banco.
3. **Simulados:** Painel → Configurar simulado → Simulado ativo → (interrupção/retomada) → Resultado → Revisão → Desempenho.
4. **Fórum:** Questão → Fórum → Responder/Denunciar → Confirmação → Fórum; fluxo de moderação no painel do administrador.
5. **Perfis:** Painel de professor → Comentário; Coordenador → Indicadores agregados; Admin → Questões / Moderação / Usuários.

**Atenção:** telas navegáveis e estados de erro demonstram especificação; não comprovam disponibilidade, criptografia, backup, desempenho ou segurança operacional.
