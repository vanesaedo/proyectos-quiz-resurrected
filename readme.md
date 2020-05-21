# Quiz... resurrected! #

## Introducción ##

_- "Sé que lo recuerdas... "_"

_- "Era el día... no, no me acuerdo. ¡O sí!... "_

_- "Definitivamente, no."_

![](https://media.giphy.com/media/TgmOF4T3OoUo7XOfAX/giphy.gif)

¡Ya te lo recuerdo yo! Era la semana pasada cuando hiciste un cuestionario con 5 preguntas...

![](https://media.giphy.com/media/TGWMFPzduIHAdc3Fxn/giphy.gif)

En esta ocasión, haremos algo que se llama _"[refactorización](https://blog.ahierro.es/refactorizacion-de-codigo/)"_ y luego añadiremos nuevas funcionalidades.

Con esto haremos que nuestra aplicación cargue y corrija tantas preguntas como queramos.

## Objetivos ##

- Aprender a refactorizar
- Hacer que nuestra aplicación de Quiz imprima y corrija tantas preguntas como le pasemos, a través de una colección de objetos.

## Requisitos ##

- Precurso Web

- Programación avanzada

- Haber realizado el proyecto [Quiz](https://github.com/TheBridge-FullStackDeveloper/proyectos-quiz)

![](https://media.giphy.com/media/l46CgZ79Eatei0Qve/giphy.gif)

## Iteraciones ##

La _"[refactorización](https://blog.ahierro.es/refactorizacion-de-codigo/)"_ no es más que cambiar el código fuente sin cambiar la funcionalidad, con el objetivo de mejorarlo,

Nos centraremos en conseguir el mismo resultado, pero sin cambiar el funcionamiento. Es decir, seguimos teniendo 5 preguntas que se corrigen.

### jueves - Pintar las 5 preguntas ###

Van a entrar en juego 2 funciones, `printQuestions` y `printQuestion`, y una colección de objetos, `questions`.

- `printQuestions` recibe la colección de preguntas `questions` y devuelve el HTML con todas las preguntas.
- `printQuestion` recibe una pregunta y devuelve el HTML de esa pregunta.
- `questions` es una colección con todas las preguntas.

1. Nos llevarnos todas las preguntas desde el HTML hasta JS, dentro de la función `printQuestions`. Ahora tenemos una función que devuelve un enorme string, con todas las preguntas, pero el comportamiento de la función no habrá cambiado.

2. Crearemos nuestra función `printQuestion`, donde pondremos una de las preguntas, completa. Con esto se nos queda igual que `printQuestions`, imprimiendo un string con una pregunta, pero una en vez de 5.

  Una vez tenemos esta pregunta, sacaremos todos los valores relevantes, en forma de objeto, como aquí.

  Ejemplo:
  ```javascript
  const question = {
    name: 'elminster',
    label: '¿Cual es el nombre mas comun del mundo?',
    answers: [
      {label: 'Un bardo', value: 'bardo'},
      {label: 'Un mercader', value: 'mercader'},
      {label: 'Un mago', value: 'mago'},
      {label: 'Un marinero', value: 'marinero'},
    ]
  }
  ```
  En este punto, tenemos `printQuestions`, `printQuestion` y una _question_

3. Haz que al ejecutar `printQuestion` con el objeto anterior _question_ como argumento, devuelva el mismo HTML. Con esto, tenemos una función que, al pasarle una pregunta, devuelve el HTML para esa pregunta.

4. Crea la colección `questions` y mete todas las preguntas ahí, con el mismo formato que tiene el objeto `question`.

5. ¡Hora de montar el puzzle!

  Una vez llegado hasta aquí, tendrás todo lo necesario: `printQuestions`, `printQuestion` y tu colección de `questions`

  El funcionamiento es el siguiente:
    - `printQuestions` se ejecuta y toma como argumento `questions`.
    - Dentro de `printQuestions` iterarás sobre dichas `questions` e imprimirás cada una de ellas con `printQuestion` en cada iteración

![](https://media.giphy.com/media/xmYbQrxezZkmk/giphy.gif)

_Premium_

Te habrás dado cuenta que todo aquello que se halla dentro de `printQuestion` es susceptible de mejorarse, como iterar para cada _answer_, crear funciones adicionales... ¡HAZLO!

### viernes - Corregir las 5 preguntas ###

Después de ayer, tu aplicación es capaz de pintar tantas preguntas como quieras. Si has utilizado las 5 preguntas originales, descubrirás que sigue funcionando, pero no así con nuevas preguntas.

Habrás deducido que la validación no tiene que ver con nada de lo que hicimos ayer, y que se halla en otro lado. Las preguntas estaban en el HTML y nosotros, sabiendo que para cambiarlas hay que hacerlo manualmente, pues podemos tener en JS las respuestas correctas y así podíamos comparar pero, ¿qué ocurriría si las preguntas vienen de un lugar misteriosos y no sabemos las respuestas?

Nuestra misión hoy será hacer que la validación sea posible para todos las preguntas que queramos. Esto se logra de la siguiente manera: En cada pregunta, de nuestra colección de preguntas, debe estar la respuesta correcta.

1. Lleva a cada pregunta su respuesta correcta.

  Ejemplo:
  ```javascript
  const question = {
    name: 'elminster',
    label: '¿Cual es el nombre mas comun del mundo?',
    answers: [
      {label: 'Un bardo', value: 'bardo'},
      {label: 'Un mercader', value: 'mercader'},
      {label: 'Un mago', value: 'mago'},
      {label: 'Un marinero', value: 'marinero'},
    ]
    correct: 'mago'
  }
  ```

2. Una vez que el usuario envíe sus resultados, iteraremos por cada uno de ellos y buscaremos dentro de la colección questions su respuesta correctabuscaremos dentro de la colección `questions` su respuesta correcta.

![](https://media.giphy.com/media/UseBZDm3O00hy/giphy.gif)

_- "¿Ves? No ha sido tan dificil"_

_-"Bueno, me he hecho un poco de caquita, ¡pero lo he terminado!"_
