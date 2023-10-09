---
title: db_close
description: Fechar uma conexão com o banco de dados SQLite que foi aberto com `db_open`.
keywords:
  - sqlite
---

<LowercaseNote />

## Descrição

 Fechar uma conexão com o banco de dados SQLite que foi aberto com [db_open](db_open).

| Name  | Description                                                                                    |
| ----- | ---------------------------------------------------------------------------------------------- |
| DB:db | O identificador da conexão de banco de dados a ser fechada (retornado por [db_open](db_open)). |

## Retornos

1: Se a função foi executada corretamente.

0: A função não foi executada. Isso pode significar que o identificador de conexão do banco de dados é inválido (não existe).

## Exemplos

```c
static DB:gDBConnectionHandle;

// ...

public OnGameModeInit()
{
    // ...

    // Crie uma conexão com um banco de dados.
    gDBConnectionHandle = db_open("example.db");

    // Se existir conexão com o banco de dados
    if (gDBConnectionHandle)
    {
        // Criou com sucesso uma conexão com o banco de dados
        print("Criou com sucesso uma conexão com o banco de dados \"example.db\".");
    }
    else
    {
        // Falha ao criar uma conexão com o banco de dados
        print("Falha ao criar uma conexão com o banco de dados \"example.db\".");
    }

    // ...

    return 1;
}

public OnGameModeExit()
{
    // Fecha a conexão com o banco de dados se existir
    if (db_close(gDBConnectionHandle))
    {
        // Limpeza extra
        gDBConnectionHandle = DB:0;
    }

    // ...

    return 1;
}
```

## Notas

:::warning

Usar um identificador inválido diferente de zero irá travar seu servidor! Obtenha um identificador de conexão de banco de dados válidos usando [db_open](db_open).

:::

## Funções relacionadas

- [db_open](db_open): Abra uma conexão com um banco de dados SQLite
- [db_close](db_close): Fecha a conexão com um banco de dados SQLite
- [db_query](db_query): Faça uma consulta no banco de dados SQLite
- [db_free_result](db_free_result): Libera memória de resultados de um db_query
- [db_num_rows](db_num_rows): Obtenha o número de linhas de uma consulta
- [db_next_row](db_next_row): Move para a próxima linha
- [db_num_fields](db_num_fields): Obtém o número de campos em uma consulta
- [db_field_name](db_field_name): Retorna o nome de um campo em um índice específico
- [db_get_field](db_get_field): Obtém o conteúdo do campo com o ID especificado da linha de resultado atual
- [db_get_field_assoc](db_get_field_assoc): Obtém o conteúdo do campo com o nome especificado da linha de resultado atual
- [db_get_field_int](db_get_field_int): Obtém o conteúdo do campo como um número inteiro com o ID especificado da linha de resultado atual
- [db_get_field_assoc_int](db_get_field_assoc_int): Obtém o conteúdo do campo como um número inteiro com o nome especificado da linha de resultado atual
- [db_get_field_float](db_get_field_float): Obtém o conteúdo do campo como um float com o ID especificado da linha de resultado atual
- [db_get_field_assoc_float](db_get_field_assoc_float): Obtém o conteúdo do campo como um float com o nome especificado da linha de resultado atual
- [db_get_mem_handle](db_get_mem_handle): Obtenha o identificador de memória para um banco de dados SQLite que foi aberto com db_open.
- [db_get_result_mem_handle](db_get_result_mem_handle): Obtenha o identificador de memória para uma consulta SQLite que foi executada com db_query.
- [db_debug_openfiles](db_debug_openfiles): A função obtém o número de conexões de banco de dados abertas para fins de depuração.
- [db_debug_openresults](db_debug_openresults): A função obtém o número de resultados de banco de dados abertos.
