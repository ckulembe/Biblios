# Pacote raiz `com.biblioteca`

Contém as quatro camadas e o ponto de entrada.

## Ponto de entrada

`MainApp` inicializa o JavaFX e monta as dependências manualmente (composition root): cria a ligação à base de dados, as implementações dos repositórios, os casos de uso e os ViewModels.

## Camadas

- `ui`
- `application`
- `domain`
- `infra`
