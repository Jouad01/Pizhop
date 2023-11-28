# DWEC EXAMEN CONTENIDO

## Sintaxis resumen

1. appendChild: Esta función del DOM se utiliza para añadir un nuevo nodo (elemento) al final de la lista de hijos de un nodo padre. El nodo que se añade se pasa como parámetro. Ejemplo:

```javascript
let newElement = document.createElement('div');
newElement.textContent = 'Soy un nuevo elemento';
document.body.appendChild(newElement);
```

2. setInterval: Esta función del BOM se utiliza para ejecutar repetidamente una función o un bloque de código a intervalos de tiempo específicos, hasta que se detiene con clearInterval o la ventana se cierra. Ejemplo:

```javascript
let interval = setInterval(() => {
    console.log('Hola');
}, 1000);
```

3. textContent: Esta propiedad del DOM representa el contenido de texto de un nodo y sus descendientes. Se puede utilizar para obtener o establecer el contenido de texto de un elemento.

```javascript
let element = document.getElementById('myElement');
console.log(element.textContent); // obtiene el contenido de texto
element.textContent = 'Nuevo contenido'; // establece el contenido de texto
```

4. querySelector: Esta función del DOM devuelve el primer elemento que coincide con un selector o grupo de selectores de CSS especificado. Si no se encuentra ningún elemento que coincida, devuelve null.

```javascript
let element = document.querySelector('#myElement');
```

5. addEventListener: Esta función del DOM se utiliza para adjuntar un controlador de eventos a un elemento sin sobrescribir los controladores de eventos existentes.

```javascript
let button = document.querySelector('button');
button.addEventListener('click', () => {
    console.log('¡Botón pulsado!');
});
```

6. removeChild: Esta función del DOM se utiliza para eliminar un nodo hijo de un elemento.

```javascript
let element = document.querySelector('div');
element.removeChild(element.firstChild);
```

7. window.location: Esta propiedad del BOM se utiliza para obtener o establecer la URL actual.

```javascript
console.log(window.location.href); // obtiene la URL actual
window.location.href = 'https://www.example.com'; // establece la URL actual
```

8. createElement: Esta función del DOM se utiliza para crear un nuevo elemento con el nombre de la etiqueta especificada.

```javascript
let newElement = document.createElement('div');
```

9. clearInterval: Esta función del BOM se utiliza para borrar un temporizador configurado con setInterval.

```javascript
let interval = setInterval(() => {
    console.log('Hola');
}, 1000);
clearInterval(interval);
```

10. getElementsByTagName: Esta función del DOM se utiliza para obtener una lista de todos los elementos con el nombre de la etiqueta especificada.

```javascript
let elements = document.getElementsByTagName('div');
```




## U1: Javascript basico




## U2: DOM y BOM

En JS el DOM representa la estructura del documento HTML como una jerarquia de objetos.
Proporciona una representacion bien estructurada que nos permite modificar el contenido y la presentacion del documento. Pueden ser modificados, eliminados o creados.

Ejemplo: 

```javascript
let element = document.getElementById('myElement');
element.textContent = 'Nuevo contenido'; 
// cambia el contenido de texto del elemento con id myElement
```

El BOM en cambio representa objetos del navegador que no están relacionados con el documento directamente.

Ejemplo:

```javascript
console.log(window.location.href); // obtiene la URL actual
window.location.href = 'https://www.example.com'; // establece la URL actual
```

Mientras que BOM se centra en los objetos del navegador como la ventana o la ubicacion, el DOM se centra en los objetos del documento como los elementos HTML.

### METODOS DEL DOM

- getElementById
- getElementsByClassName
- getElementsByTagName
- querySelector
- createElement
- appendChild
- removeChild
- querySelectorAll

### METODOS DEL BOM

- window.location
- window.open
- window.close
- window.prompt
- screen.width
- screen.height

## U3: Events y Callbacks

Los eventos y callbacks son claves en la programacion asincrona. Se conoce como programacion asincrona cuando existe una ejecucion de tareas de manera no secuencial, es decir, no se ejecutan de manera lineal de arriba a abajo. Se utilizan events y callbacks para la interactividad de las aplicaciones web.

Los eventos son acciones o sucesos que ocurren en el navegador, como hacer clic en un boton, cargar una pagina, mover el raton... Son generados por el usuario o sistema.

Un callback es una funcion que se pasa como parametro a otra funcion. Se ejecuta despues de que se complete una operacion. Se utilizan para manejar eventos y operaciones asincronas, simplemente son funciones que se pasan como argumentos a otras funciones.

Ejemplo de Evento y Callback:

Supongamos que tienes un botón en tu HTML con el id "miBoton". Puedes usar JavaScript para asignar un evento (por ejemplo, "clic") y proporcionar una función de callback para manejar ese evento.

```javascript
<button id="miBoton">Haz clic</button>
// Obtén una referencia al botón por su ID
var miBoton = document.getElementById("miBoton");

// Define una función de callback para el evento clic
function handleClick() {
  console.log("¡Se hizo clic en el botón!");
}

// Asigna el evento clic y el callback al botón
miBoton.addEventListener("click", handleClick);
```

## U4: JS nowaydays ES6 to ES11 (clousures, arrow functions, import/export, hoisting/scope)

### Closures

Un closure es una funcion que recuerda el entorno en el que se creo. Esto significa que una funcion dentro de otra funcion tiene acceso a las variables de la funcion externa, incluso despues de que la funcion externa se haya completado, es parecido a una funcion anidada.

Ejemplo:

```javascript
function init() {
  var name = 'Mozilla'; // La variable name es una variable local creada por init
  function displayName() { // displayName() es la funcion interna, un closure
    alert(name); // Usa una variable declarada en la funcion externa
  }
  displayName(); 
}
init();
```

### Arrow functions

Las arrow functions son una forma concisa de escribir funciones en JavaScript. Se escriben utilizando la sintaxis de flecha (=>), de ahí su nombre. Las arrow functions son funciones anonimas, es decir, no tienen nombre, se introdujeron en ES6.

Ejemplo:

```javascript
// Sintaxis de función tradicional
function suma(a, b) {
  return a + b;
}

// Sintaxis de función flecha
const sumaArrow = (a, b) => a + b;
```

### Import/Export

Los módulos permiten dividir el código en archivos separados, facilitando el mantenimiento y la organización del código. import y export son palabras clave utilizadas en el sistema de módulos de JavaScript introducido en ES6. 
Cuando se introducen en un script de html se debe especificar el atributo type="module" en la etiqueta script.

Ejemplo:

```javascript
// archivo1.js
export const suma = (a, b) => a + b;

// archivo2.js
import { suma } from './archivo1.js';
```

### Hoisting/Scope

El hoisting se refiere a como funcionan las variables y funciones en JavaScript. Las variables y funciones se declaran antes de que se ejecuten, esto significa que se pueden utilizar antes de declararlas. El hoisting solo funciona con variables declaradas con var, no con let o const.

Ejemplo:

```javascript
console.log(miVariable); // Imprimirá "undefined"
var miVariable = "Hola";
console.log(miVariable); // Imprimirá "Hola"
```

El scope se refiere a la visibilidad de las variables. Las variables declaradas dentro de una funcion son locales, solo se pueden acceder a ellas dentro de la funcion. Las variables declaradas fuera de una funcion son globales, se pueden acceder a ellas desde cualquier lugar del codigo.

Ejemplo:

```javascript
var miVariable = "Hola"; // Variable global
function miFuncion() {
  var miVariable = "Adios"; // Variable local
  console.log(miVariable); // Imprimirá "Adios"
}
miFuncion();
console.log(miVariable); // Imprimirá "Hola"
```

### ASYNC/AWAIT

Async/await es una forma de escribir código asíncrono en JavaScript. Async/await es una sintaxis que permite escribir código asíncrono de manera más concisa y legible. Async/await se introdujo en ES8.

Ejemplo:

```javascript
function obtenerDatos() {
  return new Promise(resolve => {
    setTimeout(() => resolve("Datos obtenidos"), 1000);
  });
}
async function ejecutarOperacion() {
  try {
    const resultado = await obtenerDatos();
    console.log(resultado);
  } catch (error) {
    console.error("Error:", error);
  }
}

ejecutarOperacion();
```


## U5: Promises (XMLHttpRequest, fetch, promises, json)

Las promises son objetos que representan el resultado eventual (es decir, antes o despues) de una operacion asincrona. Una promise puede estar en uno de los siguientes estados: pending, fulfilled o rejected. Las promises se introdujeron en ES6, son una forma de hacer operaciones asincronas más
legibles.


Ejemplo:

```javascript

function obtenerDatos() {
  return new Promise(resolve => {
    setTimeout(() => resolve("Datos obtenidos"), 1000);
  });
}

obtenerDatos()
  .then(resultado => {
    console.log(resultado);
  })
  .catch(error => {
    console.error("Error:", error);
  });
```



La funcion fetch se utiliza para hacer peticiones HTTP. Se utiliza para obtener recursos de red,
normalmente json o archivos.


Ejemplo:

```javascript
fetch('https://jsonplaceholder.typicode.com/todos/1')
  .then(response => {
    if (!response.ok) {
      throw new Error('Error en la petición: ' + response.statusText);
    }
    return response.json();
  })
  .then(data => {
    console.log('Datos obtenidos:', data);
  })
  .catch(error => {
    console.error('Error:', error.message);
  });
```

Aqui la promesa sería la siguiente:

```javascript
fetch('https://jsonplaceholder.typicode.com/todos/1')
```

- fetch realiza una solicitud GET a la URL proporcionada y devuelve una Promesa que resuelve en el objeto Response de la solicitud.

- El primer then verifica si la solicitud fue exitosa (código de estado HTTP en el rango 200-299). Si no, lanza un error.

- El segundo then convierte la respuesta a formato JSON, devolviendo otra Promesa que resuelve en los datos parseados.

- El último catch maneja cualquier error que ocurra en cualquier parte de la cadena de Promesas.


Y XMLHttpRequest es un objeto que se utiliza para intercambiar datos con un servidor. Se puede utilizar para enviar y recibir datos en diferentes formatos, incluidos JSON, XML, HTML y texto, es una API más antigua, hoy en día se utiliza fetch.# DWEC-PRACTICAR
