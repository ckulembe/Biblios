# Convenções

Regras para manter o código e a documentação consistentes.

## Idioma

- Infraestrutura técnica em inglês: `controller`, `usecase`, `repository`, `mapper`
- Domínio em português, sem acentos nos identificadores: `Livro`, `Leitor`, `Emprestimo`
- Documentação e comentários em português

## Nomes

- Casos de uso: verbo + objecto + `UseCase` (ex.: `EmprestarItemUseCase`)
- Repositórios: entidade + `Repository` (interface) e `Postgres` + entidade + `Repository` (implementação)
- ViewModels: ecrã + `ViewModel`
- Enumerações no singular, constantes em MAIÚSCULAS

## Credenciais

Nunca guardar a palavra-passe do PostgreSQL no repositório. Usar um ficheiro local ignorado pelo Git ou variáveis de ambiente, e manter apenas um modelo com valores de exemplo.

## Interface e threads

Chamadas à base de dados correm em segundo plano. A thread de interface do JavaFX nunca é bloqueada.
