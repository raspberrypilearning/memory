## Mejor resultado

Ahora guarda el mejor resultado para jugar contra tus amigos.

--- task ---

Agrega dos nuevas variables llamadas `mejor resultado`{:class="block3variables"} y `nombre`{:class="block3variables"} a tu proyecto.

--- /task ---

Cuando el juego termina porque el jugador se equivoca de secuencia, el juego debe verificar si la puntuación es más alta que el mejor resultado actual. Si es así, el juego debe guardar la puntuación como la puntuación más alta (mejor resultado), y también guardar el nombre del jugador.

--- task ---

Añade código al objeto del personaje para almacenar el `mejor resultado`{:class="block3variables"}. Pregunta también por el nombre del jugador y guárdalo en la variable `nombre`{:class="block3variables"}.

[[[generic-scratch3-high-score]]]

--- hints ---



--- hint ---

Tu nuevo código debe seguir este patrón:

Después del mensaje `Fin del juego`{:class="block3looks"} `Si`{:class="block3control"} `puntos`{:class="block3variables"} es `mayor que`{:class="block3operators"} el `mejor resultado`{:class="block3variables"} `Dar`{:class="block3variables"} a `mejor resultado`{:class="block3variables"} el valor de `puntos`{:class="block3variables"} `Preguntar`{:class="block3sensing"} el nombre del jugador `Dar`{:class="block3variables"} a `nombre`{:class="block3variables"} el valor de `respuesta`{:class="block3sensing"}

--- /hint ---

--- hint ---

Necesitas los bloques siguientes:

![ballerina](images/ballerina.png)

```blocks3
si < > entonces
end

(puntos)

(puntos)

[] > []

respuesta

(mejor resultado)

preguntar [¿Cuál es tu nombre?] y esperar

dar a [mejor resultado v] el valor [] 

dar a [nombre v] el valor [] 
```

--- /hint ---

--- hint ---

Así es como debe verse tu código al presionar el botón rojo:

![ballerina](images/ballerina.png)

```blocks3
when I receive [rojo v]
if <(item (1 v) of [secuencia v])=[1]> then
	play drum (item (1 v) of [secuencia v]) for (0.25) beats
	delete (1 v) of [secuencia v]
else
	say [¡Fin del juego!] for (1) seconds
	if < (puntos :: variables) > (mejor resultado) > then
		set [mejor resultado v] to (puntos :: variables)
		ask [¡Mejor resultado! ¿Cuál es tu nombre?] and wait
		set [nombre v] to (respuesta)
	end
	stop [todos v]
end
```

--- /hint ---

--- /hints ---

--- /task ---

¡También necesitas añadir este nuevo código al objeto del personaje para los otros tres colores!

¿Te has fijado que el código 'Fin del juego' para cada uno de los cuatro colores es exactamente el mismo?

![ballerina](images/ballerina.png)

```blocks3
decir [¡Fin del juego!] por (1) segundos
si < (puntos :: variables) > (mejor resultado) > entonces
dar a [mejor resultado v] el valor (puntos :: variables)
preguntar [¡Mejor resultado! ¿Cuál es tu nombre?] y esperar
dar a [nombre v] el valor  (respuesta)
end
detener [todos v]
```

Si necesitas cambiar cualquiera de los códigos de 'Fin del juego', por ejemplo para agregar un sonido o cambiar el mensaje '¡Fin del juego!', tienes que cambiarlo cuatro veces. Eso es molesto y lleva mucho tiempo.

En cambio, puedes definir tu propio bloque de código y usarlo en cualquier lugar de tu proyecto.

--- task ---

Haz clic en `Mis bloques`{:class="block3myblocks"}, y luego en **Crear un bloque**. Llama a este nuevo bloque `Fin del juego`{:class="block3myblocks"}.

--- /task ---

--- task ---

Añade el código del bloque `si no`{:class="block3control"} conectado al enviar `rojo`{:class="block3events"} al bloque `Fin del juego`{:class="block3myblocks"} para que se vea así:

![ballerina](images/ballerina.png)

```blocks3
definir Fin del juego
decir [¡Fin del juego!] durante (1) segundos
si < (puntos :: variables) >  (mejor resultado) > entonces
dar a [mejor resultado v] el valor (puntos :: variables)
preguntar [¡Mejor resultado! ¿Cuál es tu nombre?] y esperar
dar a [nombre v] el valor (respuesta)
end
detener [todos v]
```

--- /task ---

--- task ---

Ahora quita el código del bloque `si no`{:class="block3control"} conectado al enviar `rojo`{:class="block3events"} y añádelo al bloque `Fin del juego`{:class="block3myblocks"}:

![ballerina](images/ballerina.png)

```blocks3
when I receive [rojo v]
if <(item (1 v) of [secuencia v])=[1]> then
	play drum (\(1\) Caja v) for (0.25) beats
	delete (1 v) of [secuencia v]
else
	Fin del juego:: custom
end
```

--- /task ---

--- task ---

Prueba tu nuevo bloque jugando el juego y haciendo clic en el botón rojo en el punto equivocado de la secuencia de colores.

--- /task ---

Tu nuevo bloque `Fin del juego`{:class="block3myblocks"} es un bloque **función**, un pequeño programa que puedes usar en cualquier lugar de tu código agregando dicho bloque `Fin del juego`{:class="block3myblocks"}.

--- task ---

Reemplaza también el código del bloque `si no`{:class="block3control"} conectado al bloque `enviar`{:class="block3events"} para los otros colores con el nuevo bloque `Fin del juego`{:class="block3myblocks"}. Así es como el código para el enviar `azul`{:class="block3events"} debería verse

![ballerina](images/ballerina.png)

```blocks3
al recibir [azul v]
si < (elemento (1 v) de [secuencia v]) = [1] > entonces
tocar tambor (\(2\) Bombo v) durante (0.25) tiempos
eliminar (1 v) de [secuencia v]
si no 
Fin del juego :: custom
end
```

--- /task ---

--- task ---

Ahora añade un sonido que suene cuando se presiona el botón equivocado. ¡Sólo necesitas añadir este código una vez en el bloque `Fin del juego`{:class="block3myblocks"} que has hecho, y no cuatro veces separadas!

![ballerina](images/ballerina.png)

```blocks3
definir Fin del juego
iniciar sonido [Cough1 v]
decir [¡Fin del juego!] durante (1) segundos
si < (puntos :: variables) > (mejor resultado) > entonces 
iniciar sonido (trumpet1 v)
dar a [mejor resultado v] el valor (puntos)
preguntar [¡Mejor resultado! ¿Cuál es tu nombre?] y esperar
dar a [nombre v] el valor (respuesta)
end
detener [todos v]
```

--- /task ---