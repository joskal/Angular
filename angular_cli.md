# Angular CLI
La forma más eficiente de desarrollar en Angular es trabajando en la terminal, con [Angular CLI](https://cli.angular.io/) (Command Line Interface)
```bash
#Crear un nuevo proyecto
ng new my-app
```
La estructura del proyecto que se generará es la siguiente:
```bash
[my-app]
  [.git]
  [e2e]
  [node_modules]
  [src]

  .editorconfig
  .gitignore
  README.md
  angular.json
  package-lock.json
  package.json
  tsconfig.json
  tslint.json
```
La carpeta `[node_modules]` contiene todos los elementos (más de mil paquetes, lo que la hace bastante pesada) para controlar la aplicación en la fase de desarrollo. Podemos trasladar el
proyecto completo a otra ubicación o dispositivo sin necesidad de esta carpeta, eliminándola, ya que se puede recontruir en base al archivo `package.json` presente en la estructura.
```bash
#reconstruir el directorio [node_modules]
npm install
```

```bash
#Compilar y servir la app
cd my-app
ng serve

# Por defecto el servidor utiliza el puerto 4200
# pero podemos especificar otro.
ng serve -p 4201

# Podemos hacer que también abra la app en el navegador por defecto
ng serve -o
```
Casi todo el núcleo de la programación gira en torno al directorio `[src]`, que es donde está ubicada la aplicación de Angular como tal.
```bash
[src]
  [app]
    app.component.css
    app.component.html
    app.component.spec.ts
    app.component.ts
    app.module.ts
  [assets]
  [environments]
  browserslist
  favicon.ico
  index.html
  karma.conf.js
  main.ts
  polyfills.ts
  styles.css
  test.ts
  tsconfig.app.json
  tsconfig.spec.json
  tslint.json
```
El archivo `/src/main.ts` es el primer achivo que se ejecuta en el proyecto.

## Componentes
Los componentes son clases js con un decorador específico. Un componente es una clase que lleva a cabo una tarea concreta.
Ejemplos de componentes podrían ser la barra de navegación, barra lateral, marco de contenido, pie de página, etc... Están contenidos en la carpeta `/src/app`. Vamos a crear un componente:
```bash
# Dentro del directorio src/app crear el dir components/header
mkdir components
cd components
mkdir header
cd header
```
Dentro del directorio `src/app/components/header` crearemos el fichero `header.component.ts` con el siguiente contenido:
```js
import { Component } from '@angular/core';

@Component({
    selector: 'app-header',
    template: `<h1>Header component</h1>`
})

export class HeaderComponent{

}
```
El siguiente paso es declarar el componente en el fichero `src/app/app.module.ts` y le agregamos las siguiente línea:
```js
import { HeaderComponent } from './components/header/header.component';
```
También debemos declarar el `HeaderComponent` dentro de la sección @NgModule
```js
@NgModule({ declarations: [AppComponent, HeaderComponent ] ......
```
Con lo que el fichero finalmente quedaría de la siguiente forma:
```js
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';

import { AppComponent } from './app.component';
import { HeaderComponent } from './components/header/header.component';

@NgModule({
  declarations: [
    AppComponent,
    HeaderComponent
  ],
  imports: [
    BrowserModule
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
```
Ya sólo queda que visualicemos el nuevo componente en el navegador. Para ello debemos editar el fichero `src/app/app.component.html` y agregarle el nombre del selector `app-header` que definimos en el fichero `header.component.ts`.
```html
<app-header></app-header>
<h2>Hola mundo</h2>
<ul>
  <li>Nombre: {{ nombre }}</li>
  <li>Apellidos: {{ apellido }}</li>
</ul>
```



Las Directivas estructurales son instrucciones normales que le indican a la parte del HTML qué tiene que hacer
