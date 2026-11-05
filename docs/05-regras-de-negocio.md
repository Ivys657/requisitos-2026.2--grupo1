# 5. Regras de Negócio

| ID | Regra | Categoria | Relacionados |
|----|-------|-----------|-------------|
| RN01 | Cada usuário possui um único perfil principal: Estudante, Professor, Coordenador ou Administrador | Acesso | RF02, RF04 |
| RN02 | O e-mail deve ser único no sistema | Cadastro | RF01 |
| RN03 | Somente administradores podem cadastrar, editar, importar ou desativar questões | Questões | RF09 |
| RN04 | Toda questão deve estar associada a ano, curso/área e componente (formação geral ou conhecimento específico) | Questões | RF05 |
| RN05 | Questões desativadas não aparecem em buscas nem em novos simulados, mas permanecem em históricos já realizados | Questões | RF09, RF15 |
| RN06 | O gabarito e o comentário só são exibidos após o estudante responder a questão ou finalizar o simulado | Gabarito | RF10 |
| RN07 | O simulado é encerrado automaticamente quando o tempo termina; respostas não marcadas são contabilizadas como erradas | Simulado | RF13 |
| RN08 | Cada questão do simulado vale o mesmo peso; a nota é percentual de acertos, separando formação geral e conhecimento específico | Simulado | RF15 |
| RN09 | O simulado deve conter apenas questões do curso/área do estudante, exceto as de formação geral comuns a todos | Simulado | RF12 |
| RN10 | O estudante só visualiza suas próprias estatísticas individuais | Estatísticas | RF16 |
| RN11 | Coordenadores visualizam apenas dados agregados e anonimizados de seu curso, com agrupamentos mínimos de 5 estudantes | Privacidade | RF18, RNF08 |
| RN12 | Apenas usuários autenticados podem participar do fórum | Fórum | RF19 |
| RN13 | Conteúdos denunciados por 3 usuários diferentes ficam ocultos até revisão do moderador | Fórum | RF20, RF21 |
| RN14 | Comentários oficiais de gabarito só podem ser editados por professores autorizados ou administradores | Gabarito | RF11 |
| RN15 | Contas devem ser bloqueadas temporariamente após 5 tentativas de login inválidas consecutivas | Segurança | RF02, RNF07 |
| RN16 | Dados pessoais são tratados conforme a LGPD, com possibilidade de exclusão da conta e dos dados a pedido do titular | Privacidade | RNF08 |
| RN17 | O conteúdo das provas é utilizado respeitando a fonte oficial (INEP), com indicação de ano e edição | Legal | RNF15 |
| RN18 | Um simulado em andamento pode ser retomado por até 30 minutos após queda de conexão, sem alterar o tempo restante | Simulado | RF14 |
