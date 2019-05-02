## Desafío: mejora tu juego

### Crea más bloques

¿Ve cualquier otro código que sea el mismo que el de los cuatro botones?

```blocks3
cuando recibo [red v]
si <(elemento (1 v) de [secuencia v]) =[1]> luego
    toca el tambor (\ (1 \) Snare Drum v) durante (0.25) beats
    delete (1 v) de [secuencia v]
más
    Game Over :: custom
end

cuando recibo [azul v]
si <(elemento (1 v) de [secuencia v]) =[1]> luego
    toca el tambor (\ (2 \ ) Bass Drum v) para (0.25) beats
    delete (1 v) de [secuencia v]
else
    Game over :: custom
end
```

¿Puedes hacer otro bloque personalizado que todos los botones puedan usar?

### Otro traje

¿Puedes ver que tu juego comienza con tu personaje mostrando uno de los cuatro colores, y que el personaje siempre muestra el último color en la secuencia mientras el jugador repite la secuencia de color?

¿Puedes añadir otro traje blanco claro a tu personaje, y añadir código para que el personaje muestre este disfraz al comienzo del juego y mientras el jugador repita la secuencia?

![screenshot](images/colour-white.png)

### Nivel de dificultad

¿Puede permitir que su jugador elija entre jugar el "modo fácil" (usando solo los colores rojo y azul) y el "modo normal" (que usa los cuatro colores)?

Si lo desea, puede incluso agregar un modo 'duro', ¡que hace uso de un quinto tambor!