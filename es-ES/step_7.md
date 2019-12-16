## Desafío: mejora tu juego

### Crea más bloques

¿Ve cualquier otro código que sea el mismo que el de los cuatro botones?

```blocks3
al recibir [rojo v]
si <(elemento (1 v) de [secuencia v]) =[1]> entonces
    tocar tambor (\ (1 \) Caja v) durante (0.25) tiempos
    eliminar (1 v) de [secuencia v]
si no
    Fin del juego :: custom
fin

al recibir [azul v]
si <(elemento (1 v) de [secuencia v]) =[1]> entonces
    tocar tambor (\ (2 \) Bombo v) durante (0.25) tiempos
    eliminar (1 v) de [secuencia v]
si no
    Fin del juego :: custom
fin
```

¿Puedes hacer otro bloque personalizado que todos los botones puedan usar?

### Otro disfraz

¿Puedes ver que tu juego comienza con tu personaje mostrando uno de los cuatro colores, y que el personaje siempre muestra el último color en la secuencia mientras el jugador repite la secuencia de color?

¿Puedes añadir otro disfraz blanco a tu personaje, y añadir código para que el personaje muestre este disfraz al comienzo del juego y mientras el jugador repita la secuencia?

![screenshot](images/colour-white.png)

### Nivel de dificultad

¿Puedes permitir que tu jugador elija entre jugar en "modo fácil" (usando solo los colores rojo y azul) y el "modo normal" (que usa los cuatro colores)?

Si tú quieres, puede incluso agregar un modo 'difícil', ¡que hace uso de un quinto tambor!