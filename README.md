# Sistema de Gestão de Biblioteca

Aplicação desktop para gerir uma biblioteca: acervo, leitores, empréstimos, reservas e multas. É usada apenas pelos funcionários que operam a biblioteca; os leitores são registos geridos pelo sistema e não têm login.

## Tecnologias

- Java SE
- JavaFX (interface desktop)
- PostgreSQL (base de dados local)
- JDBC (acesso a dados)

## Arquitectura

Camadas com as dependências a apontar para dentro: `ui → application → domain ← infra`. O domínio não conhece JavaFX nem JDBC. Detalhes em [`docs/arquitetura.md`](docs/arquitetura.md).

## Perfis de acesso

- **Administrador**: contas, parâmetros, auditoria, cópias de segurança
- **Bibliotecário**: acervo, leitores, excepções, perdão de multas
- **Atendente**: balcão (empréstimos, devoluções, reservas, pagamentos)

## Estrutura do repositório

- `docs/`: documentação e diagramas
- `src/main/java/com/biblioteca/`: código-fonte por camadas
- `src/main/resources/`: FXML, CSS, scripts SQL e configuração
- `src/test/`: testes, espelhando as camadas

## Estado do projecto

- [x] Modelo de classes (UML) do acervo e dos utilizadores
- [ ] Diagrama de casos de uso
- [ ] Modelo entidade-relação
- [ ] Interfaces dos repositórios
- [ ] Casos de uso
- [ ] Ecrãs JavaFX

## Documentação

- [Arquitectura](docs/arquitetura.md)
- [Domínio](docs/dominio.md)
- [Perfis e permissões](docs/perfis-e-permissoes.md)
- [Convenções](docs/convencoes.md)
- [Diagramas](docs/diagramas/README.md)
