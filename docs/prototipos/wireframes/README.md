# Wireframes — Sistema de Apoio ao ENADE

## Objetivo

Este diretório reúne **oito wireframes de baixa fidelidade** para documentar a proposta de organização das principais telas do Sistema de Apoio ao ENADE, na Sprint 2 (M2 — Especificação e Protótipo).

Os wireframes são **representações estáticas**, em tons de cinza, destinadas à documentação da estrutura de interface. O protótipo navegável está disponível separadamente no Google Stitch: <https://stitch.google.com/preview/14068087734489227764>.

## Telas e rastreabilidade

| Nº | Tela | Casos de uso relacionados (referência inicial) |
|---|---|---|
| 01 | [Login / autenticação](01-login.png) | UC02, UC09 |
| 02 | [Cadastro do estudante](02-cadastro.png) | UC01 |
| 03 | [Painel inicial do estudante](03-painel-estudante.png) | UC07 |
| 04 | [Banco de questões](04-banco-questoes.png) | UC03, UC04, UC06 |
| 05 | [Simulado cronometrado](05-simulado.png) | UC05 |
| 06 | [Resultados e desempenho](06-resultado-desempenho.png) | UC06, UC07 |
| 07 | [Fórum de discussão](07-forum.png) | UC08, UC11, UC13 |
| 08 | [Painel de administração e coordenação](08-painel-coordenacao.png) | UC10, UC12, UC14 |

## Observações

- Todos os nomes, números, exemplos de questões, resultados, usuários, datas e endereços exibidos são **dados ilustrativos**. O domínio `enade.ufexemplo.br` é um exemplo visual, **não um endereço real do projeto**.
- Este é um **projeto acadêmico**, sem vínculo institucional ou homologação pelo MEC/INEP.
- Os wireframes não constituem telas funcionais nem evidenciam a implementação das regras de negócio. Os requisitos e regras estão especificados no SRS.
- Esta relação entre telas e casos de uso é um mapeamento inicial para fins de documentação, que deve ser validado com o SRS e a UML caso o projeto evolua.
- Para desempenho agregado de turmas, valem as restrições de privacidade definidas no SRS, independentemente dos números meramente ilustrativos nos desenhos.

## Evidência da Sprint 2

Issue de referência: [#15 — Criar wireframes das telas](https://github.com/Ivys657/requisitos-2026.2--grupo1/issues/15).

Os artefatos devem ser versionados no GitHub por meio de commit e Pull Request, sem necessidade de alterar o protótipo no Stitch.
