## Repite la secuencia

Ahora vas a añadir cuatro botones que el jugador tiene que presionar para repetir la secuencia de colores.

-- task \--- Añade cuatro nuevos sprites (objetos) a tu proyecto para representar los cuatro botones.

+ Edita los disfraces de los nuevos sprites (objetos) para que haya uno en cada uno de los cuatro colores
+ Pon los sprites (objetos) en el escenario en el mismo orden que los trajes: rojo, azul, verde, amarillo

![screenshot](images/colour-drums.png) \--- /task \---

\--- task \--- Añade código al sprite rojo para que, cuando sea pulsado, `envíe`{:class="block3events"} un mensaje 'rojo' al sprite del personaje:

![red-drum](images/red_drum.png)

```blocks3
    cuando  haces clic en este objeto
enviar (rojo v)
```

\--- /task \---

Un `enviar` {: class = "block3events"} es como un mensaje anunciado a través de un altavoz, que puedes escuchar, por ejemplo, en escuelas o supermercados. Todos los sprites (objetos) pueden escuchar el mensaje, pero sólo el sprite cuyo trabajo es responder va a hacer algo.

\--- task \---

Añade código similar a los sprites (objetos) azul, verde y amarillo para hacerlos `enviar`{:class="block3events"} mensajes sobre su propio color.

\--- /task \---

¿Te acuerdas de que `enviar` {: class = "block3events"} es como un mensaje de altavoz? Añadirás código para que sea tarea del personaje sprite responder a los mensajes `enviar`{:class="block3events"}.

\--- task \---

Cuando el sprite de tu personaje recibe el mensaje `rojo`{:class="block3events"}, el código debería verificar si el número `1` está al comienzo de la lista `secuencia`{:class="block3variables"} (lo que significa que `rojo` es el siguiente color en la secuencia).

Si `1` está al comienzo de la lista, el código debe eliminar el número de la lista, porque el jugador recordó el color correcto. De lo contrario, se acaba el juego, y el código debe `detener todos` {: class = "block3control"} para finalizar el juego.

![ballerina](images/ballerina.png)

```blocks3
al recibir [rojo v]
si <(elemento (1 v) de [secuencia v])=[1]> entonces
eliminar (1 v) de [secuencia v]
si no
decir [¡Has perdido!] durante (1) segundos
detener [todos v]
fin
```

\--- /task \---

\--- task \--- Añade al código que acabas de escribir instrucciones para que también suene un tambor cuando el sprite del personaje recibe el código `enviar`{:class="block3events"} correcto.

\--- hints \--- -- hint \--- ¿Puedes usar los números que corresponden a cada color para tocar el ritmo de tambor correcto?

+ 1 = rojo
+ 2 = azul
+ 3 = verde
+ 4 = amarillo \--- /hint \--- \--- hint \--- Sobre el bloque `eliminar 1 de secuencia`{:class="block3variables"}, añade el bloque `tocar tambor`{:class="block3sound"} para reproducir el primer sonido en la lista `secuencia`{:class="block3variables"}.

\--- /hint \--- \--- hint \--- Aquí está el código que necesitarás añadir:

```blocks3
cuando recibo [red v]
si <(elemento (1 v) de [secuencia v]) =[1]> luego
    toca el tambor (\ (1 \) Snare Drum v) durante (0.25) beats
    delete (1 v) de [secuencia v]
else
    Game over :: custom
end

```

\--- /hint \--- \--- /hints \--- \--- /task \---

\--- task \--- Duplica el código que usaste para hacer que el objeto personaje responda al mensaje ` rojo ` {: class = "block3events"}. Cambia el código duplicado para que envíe el mensaje ` azul ` {: class = "block3events"}. \--- /task \---

Cuando el sprite responde al mensaje ` azul ` {: class = "block3events"}, ¿qué parte del código debería permanecer igual y cual cambiar? Recuerda que cada color se asocia a un número.

\--- task \--- Cambia el código del objeto personaje para que responda correctamente al mensaje ` azul ` {: class = "block3events"}.

\--- hints \--- \--- hint \---

Mantén estos bloques, pero necesitas cambiarlos de alguna manera:

![ballerina](images/ballerina.png)

```blocks3
<(elemento (1 v) de [secuencia v]) = [1]>

cuando recibo [rojo v]

tocar el tambor (\ (1 \) Snare Drum v) durante (0.25) tiempos
```

\--- /hint \--- \--- hint \--- Aquí está cómo tu código debe buscar el `azul`{:class="block3events"} emitido.

![ballerina](images/ballerina.png)

```blocks3
al recibir [azul v]
si <(elemento (1 v) of [secuencia v]:: list) = [2]> entonces 
  tocar tambor (elemento (1 v) de [secuencia v]:: list) durante (0.25) pulsos
  borrar (1 v) de [secuencia v]

  decir [Game over!] por (1) segundos
  detener [todos v]
end
```

\--- /hint \--- \--- /hints \--- \--- /task \---

\--- tarea \--- Duplicar el código dos veces (para los botones verde y amarillo), y cambia las partes necesarias para que el personaje responda correctamente a las nuevas `emisiones`{:class="block3events"} . \--- /task \---

¡Recuerda probar el código! ¿Puedes memorizar una secuencia de cinco colores? ¿La secuencia es diferente cada vez?

Cuando el jugador repite toda la secuencia de colores correctamente, la ` secuencia ` {: class = "block3variables"} lista vacía y el jugador gana. Si lo deseas, también puedes mostrar algunas luces de brillantes como recompensa una vez que la lista `secuencia`{:class="block3variables"} este vacía.

\--- task \--- Agrega este código al final del código ` al hacer clic en la bandera ` {: class = "block3events"} del personaje:

![ballerina](images/ballerina.png)

```blocks3
    esperar hasta que < (longitud de [secuencia v]) = [0]>
    enviar (ganar v) y espere
```

\--- /task \---

\--- tarea \--- Cambie al escenario e importa la sonidos de la caja de ritmos ` ` u otro sonido que te guste.

[[[generic-scratch3-sound-from-library]]]

\--- /task \---

\--- tarea \--- Agrega este código para reproducir un sonido y hacer que el fondo cambie de color cuando el jugador gana.

![ballerina](images/stage.png)

```blocks3
    al recibir  [ganar v]
    tocar sonido (caja de ritmos v)
    repetir (50)
        cambiar [color v] a (25)
        esperar (0.1) segundos
    final
    quitar efectos gráficos
```

\--- /task \---