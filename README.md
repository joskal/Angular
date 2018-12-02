# Angular
Apuntes sobre Angular

Pasos para instalarlo:
1. Descargar e instalar node.js desde la [Web oficial](https://nodejs.org). Si tenemos `homebrew` instalado será mucho más sencillo:
```bash
# Desinstalar previamente node si nos da problemas
brew uninstall --ignore-dependencies node icu4c
brew install node
```
2. Instalar [typescrypt](https://www.typescriptlang.org/). Podemos hacerlo descargándola de la web oficial o bien a través del comando **npm** (Node Package Manager) con el parámetro -g (global) si hemos instalado ya el **node.js**, de la siguiente manera:
```bash
npm install -g typescript
#comprobar versión de typescript
tsc -v
```
3. El siguiente paso es instalar [**Angular CLI**](https://cli.angular.io/) (Command Line Interface) mediante **npm**.
```bash
npm install -g @angular/cli
```
La documentación la podemos encontrar [aquí](https://github.com/angular/angular-cli).

Si necesitamos actualizar **Angular** debemos desinstalar primero la versión actual.
```bash
npm uninstall -g angular-cli
npm uninstall --save-dev angular-cli

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

Aparte de trabajar en local, Podemos hacer pruebas online de nuestros códigos en [Plunker](https://plnkr.co/)

Toda la documentación está en la web oficial [Angular.io](https://angular.io/)
