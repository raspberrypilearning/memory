## Repite la secuencia

Ahora vas a agregar cuatro botones que el jugador tiene que presionar para repetir la secuencia de colores.

-- task \--- Agrega cuatro nuevos sprites a tu proyecto para representar los cuatro botones.

+ Editar los trajes de los nuevos sprites para que haya un sprite en cada uno de los cuatro colores
+ Pon los sprites en el mismo orden en el escenario que los trajes: rojo, azul, verde, amarillo

![captura de pantalla](images/colour-drums.png) \--- /task \---

\--- tarea \--- Añadir código al sprite rojo para que, cuando el sprite sea pulsado, `emita`{:class="block3events"} un mensaje 'rojo' al sprite de caracteres:

![tambor rojo](images/red_drum.png)

```blocks3
    cuando  haces click en este sprite
emite(rojo v)
```

\--- /task \---

Una emisión ` ` {: class = "block3events"} es como un mensaje anunciado a través de un altavoz, que puede escuchar, por ejemplo, en escuelas o supermercados. Todos los sprites pueden escuchar el mensaje, pero sólo el sprite cuyo trabajo es responder va a hacer algo.

\--- task \---

Añade código similar a los sprites azul, verde y amarillo para hacerlos `broadcast`{:class="block3events"} mensajes sobre su propio color.

\--- /task \---

¿Te acuerdas de que `enviar` {: class = "block3events"} es como un mensaje de altavoz? Añadirá código para que sea tarea del personaje sprite responder a los mensajes `enviar`{:class="block3events"}.

\--- task \---

Cuando el sprite de tu personaje recibe el mensaje ` rojo `, el código debería verificar si el número ` 1 ` está al comienzo de la lista (lo que significa que ` rojo ` es el siguiente color en la secuencia).

Si `1` está al comienzo de la lista, el código debe eliminar el número de la lista, porque el jugador recordó el color correcto. De lo contrario, se acabó el juego, y el código debe ` detener todo ` {: class = "block3control"} para finalizar el juego.

![bailarina](images/ballerina.png)

```blocks3
al recibir [rojo v]
si <(item (1 v) of [sequence v]:: list) = [1]> entonces 
 borrar (1 v) de [sequence v]

 decir [Game over!] por (1) segundos
 detener [todos v]
end
```

\--- /task \---

\--- tarea \--- Añadir al código que acabas de escribir para que un tambor también suene cuando el caracter sprite recibe el c'odigo correcto `broadcast`{:class="block3events"}.

\--- hints \--- \--- hint \--- ¿Puedes usar los números que corresponden a cada color para tocar el ritmo de tambor correcto?

+ 1 = rojo
+ 2 = azul
+ 3 = verde
+ 4 = amarillo \--- /hint \--- \--- hint \--- Sobre el bloque `borrar 1 de secuencia`{:class="block3variables"}, agrega el bloque `tocar tambor`{:class="block3sound"} para emitir el primer sonido en la lista `secuencia`{:class="block3variables"}.

\--- /hint \--- \--- hint \--- Aquí está el código que necesitarás:

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

\--- tarea \--- Duplique el código que usó para hacer que su sprite de personaje responda al mensaje ` rojo ` {: class = "block3events"}. Cambie el código duplicado para que envíe el mensaje ` azul ` {: class = "block3events"}. \--- /task \---

Cuando el sprite responde al mensaje ` azul ` {: class = "block3events"}, ¿qué parte del código debería permanecer igual y cual cambiar? Recuerda que cada color tiene se asocia a un número.

\--- tarea \--- Cambia el código sprite del perosnaje para que responda correctamente al ` azul ` {: class = "block3events"} mensaje.

\--- hints \--- \--- hint \---

Mantén estos bloques, pero necesitas cambiarlos de alguna manera:

![bailarina](images/ballerina.png)

```blocks3
<(elemento (1 v) de [secuencia v]) = [1]>

cuando recibo [red v]

tocar el tambor (\ (1 \) Snare Drum v) durante (0.25) tiempos
```

\--- /pista\--- \--- pista \--- Aquí está cómo tu código debe buscar el `azul`{:class="block3events"} emitido.

![bailarina](images/ballerina.png)

```blocks3
al recibir [blue v]
si <(item (1 v) of [sequence v]:: list) = [2]> entonces 
  tocar tambor (elemento (1 v) de [sequence v]:: list) durante (0.25) pulsos
  borrar (1 v) de [sequence v]

  decir [Game over!] por (1) segundos
  detener [todos v]
end
```

\--- /hint \--- \--- /hints \--- \--- /task \---

\--- tarea \--- Duplicar el código dos veces (para los botones verdes y amarillos), y cambiar las partes necesarias para que el personaje responda correctamente a las nuevas `emisiones`{:class="block3events"} . \--- /task \---

¡Recuerda probar el código! ¿Puedes memorizar una secuencia de cinco colores? ¿La secuencia es diferente cada vez?

Cuando el jugador repite toda la secuencia de colores correctamente, la secuencia ` ` {: class = "block3variables"} lista vacia y el jugador gana. Si lo desea, también puede mostrar algunas luces de brillantes como recompensa una vez que la lista `secuencia`{:class="block3variables"} este vacía.

\--- tarea \--- Agregue este código al final de su carácter ` cuando haga clic en la bandera ` {: class = "block3events"} script:

![bailarina](images/ballerina.png)

```blocks3
    espere hasta < (longitud de [secuencia v]) = [0]>
    transmisión (ganada v) y espere
```

\--- /task \---

\--- tarea \--- Cambie al escenario e importa la sonidos de la caja de ritmos ` ` u otro sonido que te guste.

[[[generic-scratch3-sound-from-library]]]

\--- /task \---

\--- tarea \--- Agrega este código para reproducir un sonido y hacer que el fondo cambie de color cuando el jugador gana.

![bailarina](images/stage.png)

```blocks3
    cuando esccho el sonido de inicio [won v]
    (caja de ritmos v)
    repetición (50)
        cambio [color v] a (25)
        espera (0.1) segundos
    final
    efectos gráficos claros
```

\--- /task \---