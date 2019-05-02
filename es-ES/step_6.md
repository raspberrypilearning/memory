## Reto: Crear más bloques

Ahora guarda la puntuación más alta para jugar contra tus amigos.

\--- tarea \--- Agrega dos nuevas variables llamadas ` puntuación alta ` {: class = "block3variables"} y ` nombre ` {: class = "block3variables"} para su proyecto. \--- / tarea \---

Cuando el juego termina porque el jugador se equivoca de secuencia, el juego debe verificar si la puntuación es más alta que la puntuación más alta actual. Si es así, el juego debería guardar la puntuación como la puntuación más alta, y también guardar el nombre del jugador.

\--- tarea \--- Añade el código a su sprite de caracteres para almacenar la `puntuación alta`{:class="block3variables"}. También pida el nombre del jugador y almacenalo en la variable `name`{:class="block3variables"}.

[[[generic-scratch3-high-score]]]

\--- pista \--- \--- pista \--- Tu nuevo código necesita seguir esta estructura:

Después del ` juego terminado ` {: class = "block3looks"} mensaje ` Si ` {: class = "block3control"} la puntuación ` ` {: class = "block3variables"} es ` mayor que ` {: class = "block3operators"} the ` high score ` {: class = "block3variables"} ` Set ` {: class = "block3variables"} the ` high score ` {: class = "block3variables"} a la puntuación ` ` {: class = "block3variables"} ` Ask ` {: class = "block3sensing"} para el nombre del jugador ` Establecer ` {: class = "block3variables"} el nombre ` ` {: class = "block3variables"} a la respuesta ` ` {: class = "block3sensing"} \--- / hint \--- \--- hint \---

Necesitas los siguientes bloques:

![bailarina](images/ballerina.png)

```blocks3
si < > luego
final

(puntuación)

(puntuación)

[] > []

respuesta

(puntuación alta)

pregunte [¿Cuál es su nombre?] y espere

series [puntuación alta v] a [] 

series [ nombre v] a [] 
```

\--- / pista\--- \--- pista \--- Así es como debe verse su código para cuando se presiona el botón rojo:

![bailarina](images/ballerina.png)

```blocks3
al recibir [blue v]
si <(item (1 v) of [sequence v] :: list) = [1]> entonces 
  tocar tambor (elemento (1 v) de [sequence v] :: list) durante (0.25) pulsos
  borrar (1 v) de [sequence v]

  decir [Game over!] por (1) segundos
  detener [todos v]
end! ¿Cuál es su nombre?] Y espere
        establezca [nombre v] a (responder)
    fin
    pare [todos v]
fin
```

\--- /hint \--- \--- /hints \--- \--- /task \---

¡Necesitas añadir este nuevo código al sprite de caracteres también para los otros tres colores!

¿Puedes ver que el código 'Game over' para cada uno de los cuatro colores es exactamente el mismo?

![bailarina](images/ballerina.png)

```blocks3
diga [Game over!] por (1) segundos
si < (puntaje :: variables) > (puntaje alto) > luego
    establece [puntaje alto v] a (puntaje :: variables)
    pregunta [puntaje alto! ¿Cuál es su nombre?] Y espere
        establezca [nombre v] a (responder)
    fin
    pare [todos v]
fin
```

Si necesita cambiar cualquiera de los códigos de 'Game over', por ejemplo, para agregar un sonido o cambiar el mensaje 'Game over', debe cambiarlo cuatro veces. Eso es molesto y desperdicia mucho tiempo.

En cambio, puedes definir tu propio bloque de código y usarlo en cualquier lugar de tu proyecto.

\--- tarea \--- Haga clic en ` Mis bloques ` {: class = "block3myblocks"}, y luego en ** Make a Block **. Llama a este nuevo bloque ` Game over ` {: class = "block3myblocks"}.

\--- /task \---

\--- tarea \--- Agregue el código de la ` else ` {: class = "block3control"} bloque conectado al rojo ` ` {: class = "block3events"} transmitido al ` Juego terminado ` El bloque {: class = "block3myblocks"} para que se vea así:

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