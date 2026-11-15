# Domínio

Resumo do modelo de classes. O diagrama completo está em `diagramas/`.

## Acervo

Raiz abstracta `ItemAcervo`, com quatro categorias abstractas:

1. **Materiais Bibliográficos e Textuais**: livros, obras de referência, periódicos, trabalhos académicos, obras raras
2. **Materiais Cartográficos e Especiais**: mapas e cartas, partituras, iconografia
3. **Materiais Multimédia e Digitais**: áudio, vídeo e imagem, recursos digitais
4. **Acervos Inclusivos e de Tecnologia Assistiva**: braille, letra ampliada e audiodescrição, jogos e materiais pedagógicos

## Interfaces transversais

- `Emprestavel` e `ConsultaLocal` (mutuamente exclusivas)
- `Reservavel`, `Multavel`, `Digital`, `Acessivel`, `Preservavel`

## Pessoas

- `Pessoa` (abstracta) → `Funcionario` (abstracta) → `Administrador`, `Bibliotecario`, `Atendente`
- `Pessoa` → `Leitor` (abstracta) → `Estudante`, `Professor`, `PublicoGeral`
- `ContaAcesso` (composição de `Funcionario`) e `RegistoAuditoria`

## Regra de modelação

Uma subcategoria só vira classe quando o comportamento muda (prazo, multa, regras de empréstimo). Se muda apenas o rótulo, usa-se uma enumeração.
