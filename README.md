# CRUD de usuários em PHP

Cadastro de usuários com **PHP + MySQL + Bootstrap 5**: criar, listar, editar e excluir.

## Arquivos

| Arquivo | Função |
|---|---|
| `config.php` | conexão com o MySQL |
| `index.php` | layout e navegação (Bootstrap) |
| `listar-usuario.php` | tabela de usuários |
| `novo-usuario.php` | formulário de cadastro |
| `editar-usuario.php` | formulário de edição |
| `salvar-usuario.php` | recebe as ações `cadastrar`, `editar` e `excluir` |

## Como rodar

1. Tenha PHP 8 e MySQL instalados.
2. Crie o banco `cadastro` e a tabela:

```sql
CREATE TABLE usuarios (
  id INT AUTO_INCREMENT PRIMARY KEY,
  nome VARCHAR(120) NOT NULL,
  email VARCHAR(120) NOT NULL,
  senha VARCHAR(255) NOT NULL,
  data_nasc DATE NOT NULL
);
```

3. Ajuste as credenciais em `config.php`.
4. Suba o servidor:

```bash
php -S localhost:8000
```

## Limitações (importante)

Projeto de estudo, escrito sem preocupação de segurança:

- **SQL montado por interpolação de string** — vulnerável a SQL injection. O correto é *prepared statements* com `mysqli` ou PDO.
- **Senha em MD5**, que não é adequado para senhas. O correto é `password_hash()` / `password_verify()`.
- Não há controle de sessão nem de permissão: qualquer visitante acessa as telas.
- Não há testes.

Serve como registro do aprendizado de PHP/MySQL, não como base para produção.
