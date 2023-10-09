---
title: db_open
description: A função é usada para abrir uma conexão com um arquivo de banco de dados SQLite, que está dentro da pasta `./scriptfiles`.
keywords:
  - sqlite
---

<LowercaseNote />

## Descrição

A função é usada para abrir uma conexão com um arquivo de banco de dados SQLite, que está dentro da pasta `./scriptfiles`.

| Name   | Description                        |
| ------ | ---------------------------------- |
| name[] | Nome do arquivo do banco de dados. |

## Retornos

Retorna o índice (começando em 1) da conexão com o banco de dados.

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

A função irá criar um novo arquivo de banco de dados SQLite, se não houve nenhum arquivo de banco de dados SQLite já existente. Feche sua conexão com o banco de dados com [db_close](db_close)!

:::

 ## Funções relacionadas

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
