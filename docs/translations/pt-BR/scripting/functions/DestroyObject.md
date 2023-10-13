---
title: DestroyObject
description: Destr�i (remove) um objeto que foi criado usando CreateObject.
tags: []
---

## Descri��o

Destr�i (remove) um objeto que foi criado usando CreateObject.

| Nome     | Descri��o                                                   |
| -------- | ----------------------------------------------------------- |
| objectid | O ID do objeto a ser destru�do. Retornado por CreateObject. |

## Retorno

Esta fun��o n�o retorna nenhum valor espec�fico.

## Exemplos

```c
public OnObjectMoved(objectid)
{
    DestroyObject(objectid);
    return 1;
}
```

## Fun��es relacionadas

- [CreateObject](CreateObject): Cria um objeto.
- [IsValidObject](IsValidObject): Verifica se um determinado objeto � v�lido.
- [MoveObject](MoveObject): Move um objeto.
- [StopObject](StopObject): Pare a movimenta��o de um objeto.
- [SetObjectPos](SetObjectPos): Define a posi��o de um objeto.
- [SetObjectRot](SetObjectRot): Define a rota��o de um objeto.
- [GetObjectPos](GetObjectPos): Localize a posi��o de um objeto.
- [GetObjectRot](GetObjectRot): Localize a rota��o de um objeto.
- [AttachObjectToPlayer](AttachObjectToPlayer): Anexa um objeto a um jogador.
- [CreatePlayerObject](CreatePlayerObject): Cria um objeto para apenas um jogador.
- [DestroyPlayerObject](DestroyPlayerObject): Destrua um objeto do jogador.
- [IsValidPlayerObject](IsValidPlayerObject): Verifica se um determinado objeto player � v�lido.
- [MovePlayerObject](MovePlayerObject): Move um objeto do jogador.
- [StopPlayerObject](StopPlayerObject): Pare a movimenta��o de um objeto do jogador.
- [SetPlayerObjectPos](SetPlayerObjectPos): Define a posi��o de um objeto do jogador.
- [SetPlayerObjectRot](SetPlayerObjectRot): Defina a rota��o de um objeto do jogador.
- [GetPlayerObjectPos](GetPlayerObjectPos): Localize a posi��o de um objeto do jogador.
- [GetPlayerObjectRot](GetPlayerObjectRot): Localize a rota��o de um objeto do jogador.
- [AttachPlayerObjectToPlayer](AttachPlayerObjectToPlayer): Anexa um objeto de jogador a um jogador.