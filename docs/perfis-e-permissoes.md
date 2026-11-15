# Perfis e permissões

Só funcionários entram no sistema. Cada perfil devolve o seu conjunto de permissões através de `obterPermissoes()`.

## Matriz

| Acção | Administrador | Bibliotecário | Atendente |
|---|:-:|:-:|:-:|
| Gerir contas de funcionários | ✓ | — | — |
| Configurar parâmetros | ✓ | — | — |
| Auditoria e cópias de segurança | ✓ | — | — |
| Registar, editar, abater e classificar itens | ✓ | ✓ | — |
| Registar e editar leitores | ✓ | ✓ | só pré-registo |
| Suspender ou reactivar leitor | ✓ | ✓ | — |
| Emprestar, devolver e renovar | ✓ | ✓ | ✓ |
| Gerir reservas | ✓ | ✓ | ✓ |
| Registar pagamento de multa | ✓ | ✓ | ✓ |
| Perdoar multa e autorizar excepções | ✓ | ✓ | — |
| Consultar acervo e leitores | ✓ | ✓ | ✓ |
| Relatórios | globais | operacionais | — |

## Regras de segurança

- Palavras-passe guardadas só como hash com sal (BCrypt ou Argon2)
- Bloqueio da conta após tentativas falhadas consecutivas
- Mudança de palavra-passe obrigatória no primeiro acesso
- Acções sensíveis registadas na auditoria
- Desactivar registos em vez de os apagar
