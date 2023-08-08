<style>
    table {
        border-collapse: collapse;
        width: 100%;
    }
    
    th, td {
        border: 1px solid black;
        padding: 8px;
        text-align: left;
    }
    
    th {
        background-color: #f2f2f2; /* Color de fondo para encabezados */
    }
    
    .column-color {
        background-color: #ffd700; /* Color de fondo para la columna específica */
    }
</style>
# QA Tester
#### Francisco Magdiel Asicona Mateo magdielasicona@gmail.com

| Problemas | Errores | Descripción | Solución | Descripción | Línea |
| --- | --- | --- | --- | --- | --- |
| Error la ingresar números | guessSubmit.addeventListener('click', checkGuess); | Evento estaba escrita de forma incorrecta, addeventListener por addEventListener, la palabra evento era Event ahora con el cambió funcionó la forma esperada | guessSubmit.addEventListener('click', checkGuess); | Se cambió event por Event | 94 |
| Error al llamar función para validar números | const lowOrHi = document.querySelector('lowOrHi'); | Esta mal escrita ya que no llevaba el punto al principio (’.lowOrHi’), eso hacía que se produjera un error ahora que se coloco el punto funcionó la forma esperada | const lowOrHi = document.querySelector('.lowOrHi'); | Se coloco el punto (’.lowOrHi’) | 49 |
| Error al resetar el boton “Comienza un juego nuevo” | resetButton.addeventListener('click', resetGame); | vento estaba escrita de forma incorrecta, addeventListener por addEventListener, la palabra evento era Event ahora con el cambió funcionó la forma esperada | resetButton.addEventListener('click', resetGame); | Se cambió event por Event | 94 |
| El tipo de dato era incompatible | userGuess === randomNumber | El tipo de datos era incompatible ya que el ingreso de datos es en string y para la comparación se necesitan que ambos sean de enteros o string, entonces lo mejor era convertirlos en int ambas variables. Ahora ya realiza la comparación correcta | parseInt(userGuess) === parseInt(randomNumber) | Ambas variables se casteo a int | 72 |
| La logica de comparación esta la reves | if(userGuess === randomNumber), else if(guessCount === ATTEMPS)  | Esas dos líneas estaban validando pero de forma incorrecta, ya que se comparaba el userGuess con el número random pero para cuando pierda el jugador, al que igual que guessCount con ATTEMPS cuando encontraba el número. Ahora que se realizó el cambio ya valida de forma correcta. | if(guessCount === ATTEMPS), else if (userGuess === randomNumber) | Se cambió el orden de las validaciones y se agrego la lógica correcta | 67, 72 |
| 5 Intentos | const ATTEMPS = 5; | El número de intentos solo era de 5 intentos, se cambió a 10, ahora funciona con 10 intentos. | const ATTEMPS = 10; | Se cambió el número de intentos a 10 | 46 |
| Color de número incorrecto | lastResult.style.backgroundColor = 'green'; | El color era verde, ahora se cambió a negro para mostrar el mensaje con ese color. | lastResult.style.backgroundColor = 'black'; | Se cambió el color para desplegar el mensaje de forma correcta | 78 |
| Color de número correcto | lastResult.style.backgroundColor = 'red'; | El color era rojo, ahora se cambió a verde para mostrar el mensaje con ese color. | lastResult.style.backgroundColor = 'green'; | Se cambió el color para desplegar el mensaje de forma correcta | 74 |
| Color de llega el límite de intentos | lastResult.style.backgroundColor = 'black'; | El color era negro, ahora se cambio a rojo para mostrar el mensaje con ese color. | astResult.style.backgroundColor = 'red'; | Se cambió el color para desplegar el mensaje de forma correcta | 69 |
| Validar el ingreso de dato que no sea entero | No se había código de validación | Se agregó una validación para que solo sea permitido el ingreso de números enteros positivos, si no cumple con eso muestra un alert que dice que se debe de ingresar un número válido y no cuenta como intento el ingreso del dato inválido | (!isNaN(userGuess) && userGuess != "" && /^\d+$/.test(userGuess) | Se agregó una validación donde se valido el ingreso de un numero entero con isNan, que no sea “ “, y se agrego una expresión regular para validar que sean dígitos también. | 60 |