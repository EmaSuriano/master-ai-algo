# master-ai-algo

> [Link al Google Colab](https://colab.research.google.com/github/EmaSuriano/master-ai-algo/blob/main/Seminario_Algoritmos.ipynb)

## Problema 1. Organizar sesiones de doblaje(I)

- Se precisa coordinar el doblaje de una película. Los actores del doblaje deben coincidir en las tomas en las que sus personajes aparecen juntos en las diferentes tomas.
- Los actores de doblaje cobran toda la misma cantidad por cada día que deben desplazarse hasta el estudio de grabación independientemente del número de tomas que se graben.
- No es posible grabar más de 6 tomas por día.
- El objetivo es planificar las sesiones por día de manera que el gasto por los servicios de los actores de doblaje sea el menor posible. Los datos son:

### Datos

- Número de actores: 10
- Número de tomas : 30
- Actores/Tomas : https://bit.ly/36D8IuK
  - 1 indica que el actor participa en la toma
  - 0 en caso contrario

| Toma  | 1   | 2   | 3   | 4   | 5   | 6   | 7   | 8   | 9   | 10  | Total |
| ----- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ----- |
| 1     | 1   | 1   | 1   | 1   | 1   | 0   | 0   | 0   | 0   | 0   | 5     |
| 2     | 0   | 0   | 1   | 1   | 1   | 0   | 0   | 0   | 0   | 0   | 3     |
| 3     | 0   | 1   | 0   | 0   | 1   | 0   | 1   | 0   | 0   | 0   | 3     |
| 4     | 1   | 1   | 0   | 0   | 0   | 0   | 1   | 1   | 0   | 0   | 4     |
| 5     | 0   | 1   | 0   | 1   | 0   | 0   | 0   | 1   | 0   | 0   | 3     |
| 6     | 1   | 1   | 0   | 1   | 1   | 0   | 0   | 0   | 0   | 0   | 4     |
| 7     | 1   | 1   | 0   | 1   | 1   | 0   | 0   | 0   | 0   | 0   | 4     |
| 8     | 1   | 1   | 0   | 0   | 0   | 1   | 0   | 0   | 0   | 0   | 3     |
| 9     | 1   | 1   | 0   | 1   | 0   | 0   | 0   | 0   | 0   | 0   | 3     |
| 10    | 1   | 1   | 0   | 0   | 0   | 1   | 0   | 0   | 1   | 0   | 4     |
| 11    | 1   | 1   | 1   | 0   | 1   | 0   | 0   | 1   | 0   | 0   | 5     |
| 12    | 1   | 1   | 1   | 1   | 0   | 1   | 0   | 0   | 0   | 0   | 5     |
| 13    | 1   | 0   | 0   | 1   | 1   | 0   | 0   | 0   | 0   | 0   | 3     |
| 14    | 1   | 0   | 1   | 0   | 0   | 1   | 0   | 0   | 0   | 0   | 3     |
| 15    | 1   | 1   | 0   | 0   | 0   | 0   | 1   | 0   | 0   | 0   | 3     |
| 16    | 0   | 0   | 0   | 1   | 0   | 0   | 0   | 0   | 0   | 1   | 2     |
| 17    | 1   | 0   | 1   | 0   | 0   | 0   | 0   | 0   | 0   | 0   | 2     |
| 18    | 0   | 0   | 1   | 0   | 0   | 1   | 0   | 0   | 0   | 0   | 2     |
| 19    | 1   | 0   | 1   | 0   | 0   | 0   | 0   | 0   | 0   | 0   | 2     |
| 20    | 1   | 0   | 1   | 1   | 1   | 0   | 0   | 0   | 0   | 0   | 4     |
| 21    | 0   | 0   | 0   | 0   | 0   | 1   | 0   | 1   | 0   | 0   | 2     |
| 22    | 1   | 1   | 1   | 1   | 0   | 0   | 0   | 0   | 0   | 0   | 4     |
| 23    | 1   | 0   | 1   | 0   | 0   | 0   | 0   | 0   | 0   | 0   | 2     |
| 24    | 0   | 0   | 1   | 0   | 0   | 1   | 0   | 0   | 0   | 0   | 2     |
| 25    | 1   | 1   | 0   | 1   | 0   | 0   | 0   | 0   | 0   | 1   | 4     |
| 26    | 1   | 0   | 1   | 0   | 1   | 0   | 0   | 0   | 1   | 0   | 4     |
| 27    | 0   | 0   | 0   | 1   | 1   | 0   | 0   | 0   | 0   | 0   | 2     |
| 28    | 1   | 0   | 0   | 1   | 0   | 0   | 0   | 0   | 0   | 0   | 2     |
| 29    | 1   | 0   | 0   | 0   | 1   | 1   | 0   | 0   | 0   | 0   | 3     |
| 30    | 1   | 0   | 0   | 1   | 0   | 0   | 0   | 0   | 0   | 0   | 2     |
| TOTAL | 22  | 14  | 13  | 15  | 11  | 8   | 3   | 4   | 2   | 2   |
