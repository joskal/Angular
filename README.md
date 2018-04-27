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
Typescript se encarga de compilar un archivo con la extensión **.ts** dando como resultado un archivo javascript con la extensión **.js** .
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
