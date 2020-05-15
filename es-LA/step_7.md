## Desafío: mejora tu juego

### Crea más bloques

¿Ves otra parte de código que sea la misma que el de los cuatro botones?

```blocks3
when I receive [red v]
if <(item (1 v) of [sequence v])=[1]> then
    play drum (\(1\) Snare Drum v) for (0.25) beats
    delete (1 v) of [sequence v]
else
    Game Over :: custom
end

when I receive [blue v]
if <(item (1 v) of [sequence v])=[1]> then
    play drum (\(2\) Bass Drum v) for (0.25) beats
    delete (1 v) of [sequence v]
else
    Game over :: custom
end
```

¿Puedes hacer otro bloque personalizado que todos los botones puedan usar?

### Otro disfraz

¿Puedes ver que tu juego comienza con tu personaje mostrando uno de los cuatro colores, y que el personaje siempre muestra el último color en la secuencia mientras el jugador repite la secuencia de color?

¿Puedes añadir otro disfraz blanco a tu personaje, y añadir código para que el personaje muestre este disfraz al comienzo del juego y mientras el jugador repita la secuencia?

![captura de pantalla](images/colour-white.png)

### Nivel de dificultad

¿Puedes permitir que tu jugador elija entre jugar en "modo fácil" (usando solo los colores rojo y azul) y el "modo normal" (que usa los cuatro colores)?

Si quieres, puedes incluso agregar un modo 'difícil', ¡que use un quinto tambor!