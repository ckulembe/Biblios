# Arquitectura

O sistema usa arquitectura em camadas, MVVM na interface e o padrão Repository na persistência.

## Camadas

| Camada | Responsabilidade |
|---|---|
| `ui` | Ecrãs JavaFX, controladores e ViewModels |
| `application` | Casos de uso, DTOs, sessão e permissões, fronteiras transaccionais |
| `domain` | Entidades, regras de negócio, interfaces dos repositórios |
| `infra` | JDBC, ligação ao PostgreSQL, BCrypt, mapeadores |

## Regra de dependências

As dependências apontam sempre para dentro. `domain` não importa nada de `ui`, `application` ou `infra`. As interfaces dos repositórios vivem em `domain/repository` e as implementações em `infra/repository` (inversão de dependências).

## Modelo de domínio rico

A lógica de negócio fica dentro das entidades e dos serviços de domínio. Os casos de uso apenas orquestram: carregam objectos, chamam as regras, gravam e controlam a transacção.

## Serviço de domínio vs caso de uso

- **Serviço de domínio**: regra que envolve várias entidades mas não é um fluxo completo (ex.: cálculo de multas)
- **Caso de uso**: fluxo de ponta a ponta com permissões, repositórios e transacção (ex.: emprestar um item)

## Padrões previstos

- Repository
- Strategy (multas e prazos)
- Factory (criar e reconstruir itens)
- Builder
- Observer (properties do JavaFX)
- DTO

## Cuidados

- Operações de base de dados em segundo plano (`Task` do JavaFX), nunca na thread de interface
- A transacção pertence ao caso de uso, não ao repositório
- Permissões verificadas na camada de aplicação, não só na interface
