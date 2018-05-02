# Angular
Apuntes sobre Angular

Pasos para instalarlo:
1. Descargar e instalar node.js desde la [Web oficial](https://nodejs.org)
2. Instalar [typescrypt](https://www.typescriptlang.org/). Podemos hacerlo descargándola de la web oficial o bien a través del comando **npm** (Node Package Manager) con el parámetro -g (global) si hemos instalado ya el **node.js**, de la siguiente manera:
`npm install -g typescript`. El comando `tsc -v` nos dirá qué versión de typescrypt hemos instalado.
3. El siguiente paso es instalar [**Angular CLI**](https://cli.angular.io/) (Command Line Interface) mediante **npm**.
```bash
npm install -g @angular/cli
```
La documentación la podemos encontrar [aquí](https://github.com/angular/angular-cli).

Si necesitamos actualizar **Angular** debemos desinstalar primero la versión actual.
```bash
npm uninstall -g @angular/cli
npm cache verify
# if npm version is < 5 then use `npm cache clean`
npm install -g @angular/cli@latest
```
Si nos reporta algún error quizá debamos actualizar también **npm** (ver [doc. oficial](https://docs.npmjs.com/getting-started/fixing-npm-permissions) )
```bash
# imprimir versión de npm
npm -v
npm install npm@latest -g
```
También haremos uso del framework [ionic](https://ionicframework.com/).
```bash
npm install -g ionic
```
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
* Opcional. los opcionales van precedidos de **?**. 
