---
title: RemoveBuildingForPlayer
description: Remove um modelo de San Andreas para um �nico jogador em um raio espec�fico.
tags: ["player"]
---

<VersionWarn version='SA-MP 0.3d' />

## Descri��o

Remove um modelo de San Andreas para um �nico jogador em um raio espec�fico.

| Nome          | Descri��o                                                                             |
| ------------- | ------------------------------------------------------------------------------------- |
| playerid      | O ID do jogador para o qual remover os objetos.                                       |
| modelid       | O modelo a ser removido.                                                              |
| Float:fX      | A coordenada X em torno da qual os objetos ser�o removidos.                           |
| Float:fY      | A coordenada Y em torno da qual os objetos ser�o removidos.                           |
| Float:fZ      | A coordenada Z em torno da qual os objetos ser�o removidos.                           |
| Float:fRadius | O raio ao redor do ponto especificado para remover objetos com o modelo especificado. |

## Retorno

Essa fun��o n�o retorna um valor espec�fico.

## Exemplos

```c
public OnPlayerConnect(playerid)
{
    // Quando o jogador se conectar, os objetos com o modelo 615 ser�o removidos dentro de um
    // raio de 200.0 metros do ponto 0.0, 0.0, 0.0, que � o centro de San Andreas(mapa).
    RemoveBuildingForPlayer(playerid, 615, 0.0, 0.0, 0.0, 200.0);
    return 1;
}

public OnPlayerConnect(playerid)
{
    // Quando o jogador se conectar, todos os objetos do mapa ser�o removidos.
    RemoveBuildingForPlayer(playerid, -1, 0.0, 0.0, 0.0, 6000.0);
    return 1;
}
```

## Notas

:::tip

No SA-MP 0.3.7 voc� pode usar -1 no modelid para remover todos os objetos dentro do raio especificado.

:::

:::warning

H� um limite de cerca de 1000 linhas/objetos. N�o h� solu��o alternativa. Ao remover o mesmo objeto para um jogador, eles travar�o. Comunente, os jogadores travam ao se reconectar ao servidor porque o servidor remove o objeto no OnPlayerConnect.

:::

## Fun��es relacionadas

- [DestroyObject](DestroyObject): Destrua um objeto.
- [DestroyPlayerObject](DestroyPlayerObject): Destrua um objeto para um jogador.
