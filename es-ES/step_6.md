## Puntaje mayor

Ahora guarda la puntuación más alta para jugar contra tus amigos.

\--- task \--- Agrega dos nuevas variables llamadas ` puntaje mayor ` {: class = "block3variables"} y ` nombre ` {: class = "block3variables"} a tu proyecto. \--- /task \---

Cuando el juego termina porque el jugador se equivoca de secuencia, el juego debe verificar si la puntuación es más alta que la puntuación más alta actual. Si es así, el juego debe guardar la puntuación como la puntuación más alta, y también guardar el nombre del jugador.

\--- task \--- Añade el código a tu objeto personaje para almacenar el `puntaje mayor`{:class="block3variables"}. También pide el nombre del jugador y guárdalo en la variable `nombre`{:class="block3variables"}.

[[[generic-scratch3-high-score]]]

\--- hints \--- \--- hint \--- Tu nuevo código necesita seguir esta estructura:

Después del mensaje ` ¡Fin del juego! ` {: class = "block3looks"} ` Si ` {: class = "block3control"} el ` puntaje ` {: class = "block3variables"} es ` mayor que ` {: class = "block3operators"} el ` mayor puntaje ` {: class = "block3variables"} `Dar ` {: class = "block3variables"} a ` mayor puntaje ` {: class = "block3variables"} el valor de `puntaje ` {: class = "block3variables"} ` Preguntar ` {: class = "block3sensing"} el nombre del jugador ` Dar a ` {: class = "block3variables"} ` nombre` {: class = "block3variables"} el valor de ` respuesta ` {: class = "block3sensing"} \--- / hint \--- \--- hint \---

Necesitas los siguientes bloques:

![bailarina](images/ballerina.png)

```blocks3
si < > entonces
final

(puntaje)

(puntaje)

[] > []

respuesta

(puntaje mayor)

preguntar [¿Cuál es tu nombre?] y esperar

dar a [puntaje mayor v] el valor [] 

dar a [ nombre v] el valor [] 
```

\--- /hint \--- \--- hint \--- Así es como debe verse tu código al presionar el botón rojo:

![bailarina](images/ballerina.png)

```blocks3
al recibir [rojo v]
si <(elemento (1 v) of [secuencia v] :: list) = [1]> entonces 
  tocar tambor (elemento (1 v) de [secuencia v] :: list) durante (0.25) pulsos
  eliminar (1 v) de [secuencia v]
si no
  decir [¡Fin del juego!] por (1) segundos
  si < (puntaje:: variables) > (puntaje mayor) > entonces
  dar a [puntaje mayor v] el valor (puntaje :: variables)!
  preguntar [¡Puntaje mayor! ¿Cuál es tu nombre?] Y esperar
        dar a  [nombre v] el valor (respuesta)
    fin
    detener [todos v]
fin
```

\--- /hint \--- \--- /hints \--- \--- /task \---

¡También necesitas añadir este nuevo código al objeto personaje para los otros tres colores!

¿Puedes ver que el código 'Fin del juego' para cada uno de los cuatro colores es exactamente el mismo?

![bailarina](images/ballerina.png)

```blocks3
decir [¡Fin del juego!] por (1) segundos
si < (puntaje :: variables) > (puntaje mayor) > entonces
    dar a [puntaje mayor v] el valor (puntaje :: variables)
    preguntar [¡Puntaje mayor! ¿Cuál es tu nombre?] Y esperar
        dar a [nombre v] el valor  (respuesta)
    fin
    detener [todos v]
fin
```

Si necesitas cambiar cualquiera de los códigos de 'Fin del juego', por ejemplo, para agregar un sonido o cambiar el mensaje '¡Fin del juego!', debe cambiarlo cuatro veces. Eso es molesto y desperdicia mucho tiempo.

En cambio, puedes definir tu propio bloque de código y usarlo en cualquier lugar de tu proyecto.

\--- task \--- Haz clic en ` Mis bloques ` {: class = "block3myblocks"}, y luego en ** Crear un bloque **. Llama a este nuevo bloque ` Fin del juego ` {: class = "block3myblocks"}.

\--- /task \---

\--- task \--- Agrega el código del bloque ` si no` {: class = "block3control"} conectado a enviar `rojo ` {: class = "block3events"} al bloque ` Fin del juego ` {: class = "block3myblocks"} para que se vea así:

![bailarina](images/ballerina.png)

```blocks3
defina Juego por encima de
diga [Juego terminado!] por (1) segundos
si < (puntaje :: variables) > (puntaje alto) > luego
    establece [puntaje alto v] a (puntaje :: variables)
    pregunte [puntaje alto ! ¿Cuál es su nombre?] Y espere
        establezca [nombre v] a (responder)
    fin
    pare [todos v]
fin
```

\--- /task \---

\--- tarea \--- Agregue el código de la ` else ` {: class = "block3control"} bloque conectado al rojo ` ` {: class = "block3events"} transmitido al ` Juego terminado ` El bloque {: class = "block3myblocks"} para que se vea así:

![bailarina](images/ballerina.png)

```blocks3
cuando recibo [red v]
si <(elemento (1 v) de [secuencia v]) =[1]> luego
    toca el tambor (\ (1 \) Snare Drum v) durante (0.25) beats
    delete (1 v) de [secuencia v]
else
    Game over :: custom
end
```

\--- /task \---

\--- tarea \--- Prueba tu nuevo bloque jugando el juego y haciendo clic en el botón rojo en el punto equivocado en la secuencia de colores. \--- / tarea \---

Tu nuevo bloque `Game over`{:class="block3myblocks"} es un bloque **function**, un pequeño script que puedes usar en cualquier lugar que quieras en tu código agregando el bloque `Game over`{:class="block3myblocks"} en.

\--- tarea \--- También reemplaza el código en ` else ` {: class = "block3control"} bloque conectado a las transmisiones ` ` {: class = "block3events"} para los otros colores con su nuevo ` Game over ` {: class = "block3myblocks"} block. Aquí está el código para el mensaje `azul`{:class="block3events"} debe ser

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

\--- /task \---

\--- tarea \--- Ahora añade un sonido que suena cuando se presiona el botón equivocado. Sólo necesitas añadir este código una vez en el bloque `Fin dle juego`{:class="block3myblocks"} que has hecho, y no cuatro veces separadas!

![bailarina](images/ballerina.png)

```blocks3
definir Fin dle juego
sonido inicial [Cough1 v]
decir [Game over!] durante (1) segundos
si < (puntuación :: variables) > (puntuación alta) > luego
    reproducir sonido (trompeta 1 v)
    set [puntuación alta v] a (puntuación)
    pregunte [Puntuación alta! ¿Cuál es su nombre?] Y espere
        establezca [nombre v] a (responder)
    fin
    pare [todos v]
fin
```

\--- /task \---