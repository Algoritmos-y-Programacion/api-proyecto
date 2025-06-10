# API Proyecto: Buscaminas 💣

Base path `https://raw.githubusercontent.com/Algoritmos-y-Programacion/api-proyecto/refs/heads/main`

## `GET /config.json`

Respuesta esperada:

```json
{
  "global": {
    "board_size": [8, 8],
    "quantity_of_mines": {
      "easy": 0.1,
      "medium": 0.3,
      "hard": 0.6,
      "impossible": 0.8
    }
  }
}
```

Esto represeta las dimensiones del tablero, y el total de casillas dado, por ejemplo, `global.board_size` debera generar un tablero de 8x8 y un total de 64 casillas

La propiedad `global.quantity_of_mines` determina el porcentaje de minas en función de la dificultad que seleccione el jugar y el tamaño del tablera, para un 8x8 el juego en nivel _medium_ debera tener `8*8*0.6 = 38.4` lo que equivale a 38 minas en el tablero.

## `GET /leaderboard.json`

```json
[
  {
    "first_name": "Jose",
    "last_name": "Quevedo",
    "time": 15.5
  }
]
```

La respuesta de este endpoint es una lista con el leaderboard inicial del juego, el tiempo `response[i].time` esta dado en minutos, por lo que `15.5` equivale a 15min y 30s
