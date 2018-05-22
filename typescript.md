## Typescript
Typescript es un superset de Javascript que añade capacidades de POO (Programación Orientada a Objetos), como son el tipado estático y las clases. Typescript se encarga de compilar un archivo con la extensión **.ts** dando como resultado un archivo javascript con la extensión **.js** .
```bash
tsc app1.ts
#resultado: app1.js
```
Podemos pedirle a typescript que compile automáticamente el archivo que estamos editando cada que grabemos los cambios, para así evitar tener que escribir la misma sentencia continuamente.
```bash
#Compilar en modo observador (watching)
tsc app1.ts -w
```
Podemos compilar todos archivos **.ts** del directorio actual:
```bash
tsc -init
#nos generará el archivo tsconfig.json
```
Una vez que tengamos el archivo **json**, solo tendremos que escribir **tsc** y compilará todos los archivos **ts**.

También podemos usar el modo observador para compilar todos los archivos **.ts** a medida que se vayan grabando.
```bash
tsc -w
```

## let & const
**let** es el equivalente a **var** en javascript. La diferencia está en que en **let** el alcance está dentro del bloque en que se declare la variable **{}**. Si construimos un bloque anidado y volvemos a declarar la misma variable con **let**, no se considerará la misma variable.

**const** nos permitirá declarar constantes. Por convención las constantes van siempre en mayúsculas.

## Tipos de datos
En Typescript los tipos de datos pueden ser implícitos (al asignar el valor, toma el tipo) o explícito (declarar el tipo junto con el nombre de la variable **let nombre:tipo**). Se recomienda declarar las variables explícitamente.
```typescript
let nombre:string = "Jose";
let numero:number = 123;
let booleano:boolean = true;

let hoy:Date = new Date()
hoy = new Date("2018-10-10");

let cualquiera:any;
cualquiera = nombre;
cualquiera = numero;
cualquiera = booleano;
cualquiera = hoy;

let spiderman = {
  nombre: "Peter",
  edad: 20
}
```
## Plantillas de cadena de texto (\`backtick\`)
Este tipo evaluará el contenido encerrado entre estos caracteres  **\`{ expresion js }\`**. Devolverá el contenido de la variable o evaluará una expresión javascript.
```typescript
let nombre:string = "Jose";
let apellido:string = "Garcia";
let edad:number = 20;

let texto = `Hola, ${ nombre } ${ apellido }. Tienes ${ edad } años`;
console.log(texto);
```

## Funciones (parámetros)
En typescript las funciones pueden recibir tres tipos de parámetos:
* Obligatorio.
* Por defecto. Si no le mandamos el parámetro tomará el valor que le indiquemos **objeto:string = "batsignal"**
* Opcional. El nombre va precedido de ?. **momento?:string**
```typescript
// Parámetros de función

function activar( quien    : string,               // Parámetro obligatorio
                  objeto   : string = "batsignal", // Parámetro por defecto
                  momento? : string                // Parámetro opcional
                  ){
    let mensaje:string;
    momento? true : momento="";
    mensaje = `${ quien } activó la ${ objeto } ${ momento }`;

    console.log(mensaje);
}

activar("Gordon","batiseñal","por la tarde");
```

## Interfaces
Una interface es una plantilla de variables declaradas con su correspondiente tipo que nos permitirá ahorrar el tener que incluirlas en los parámetros de una función, al sustituirlos por el nombre de la interface.
```typescript
let wolverine:Xmen {
	
}
```


## Funciones Lambda o de flecha
Las funciones lambda son anónimas.
```typescript
//Funcion anónima normal.
let funcionNormal = function(a:string){return a;}

//Funcion flecha
let funcionFlecha = ( a:string ) => a.toUpperCase();


console.log("Funcion Normal:" + funcionNormal("jose"));
console.log("Funcion flecha:" + funcionFlecha("callealta"))

```

## Desestructuración de objetos y arrays.
Consiste en volcar a nombres de variables el contenido tanto de objetos como de arrays. Hay que tener en cuenta que a la hora de aplicarlo a un objeto los nombres de variables deben coincidir con los nombres de las propiedades del objeto. Con los arrays, la asignación es secuencial.
```typescript
//objeto
let avenger = {
	nombre:"Steve",
	clave:"Capitan_America",
	poder:"superfuerza"
}
//Desestructuración de objeto
let {nombre,clave,poder} = avenger;


//Array
let avengers:string[]=[ "Thor","Steve","Tony"];
//Desestructuracion del array
let [ thor, capi, ironman ] = avengers;

console.log("Desestructuracion del objeto avenger: ", nombre,clave,poder);
console.log("Desestructuracion del array avengers: ", thor,capi,ironman);

```

## Promises
El objeto Promise (Promesa) es usado para opeaciones asíncronas. Una promesa representa un valor que puede estar disponible ahora, en el futuro, o nunca.
```typescript
  // Llamamos a resolve(...) cuando lo que estabamos haciendo finaliza con éxito, y reject(...) cuando falla.
  // En este ejemplo, usamos setTimeout(...) para simular código asíncrono. 
  // En la vida real, probablemente uses algo como XHR o una API HTML5.

let miPrimeraPromise = new Promise((resolve, reject) => {
  setTimeout(function(){
    resolve("¡Éxito!"); }, 250);
});

  // succesMessage es lo que sea que pasamos en la función resolve(...) de arriba.
miPrimeraPromise.then((successMessage) => {
  console.log("¡Sí! " + successMessage);
});
```
###### [fuente: MDN Web Docs](https://developer.mozilla.org/es/docs/Web/JavaScript/Referencia/Objetos_globales/Promise)

## POO (Programación Orientada a Objetos)
Un constructor de clase es una función que vuelca los parámetros que le indiquemos a las propiedades de la clase que definamos.
```typescript
// Se define la clase
class Avenger{
	nombre: string = "noname"; //valor por defecto
	equipo:string;
	nombreReal:string;
	puedePelear:string;
	peleasGanadas:string;
	constructor( nombreAvenger:string, equipoAvenger:string ){
		this.nombre=nombreAvenger;
		this.equipo=equipoAvenger;
	}
}

// se crea una instancia de la Clase
let antman:Avenger=new Avenger( "antman","Justicia" );

console.log(antman);
console.log(antman.nombre);
console.log(antman.equipo);
console.log(antman.nombreReal);

```
