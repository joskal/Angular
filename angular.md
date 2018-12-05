# Angular
La forma más eficiente de desarrollar en Angular es trabajando en la terminal, con [Angular CLI](https://cli.angular.io/) (Command Line Interface)
```bash
#Crear un nuevo proyecto
ng new my-app
```
La estructura del proyecto que se generará es la siguiente:
```bash
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
Casi todo el núcleo de la programación girará en torno al directorio `[src]` donde están ubicados los componentes y las directivas estructurales.

## Componentes
Los componentes son clases js con un decorador específico. Un componente es una clase que lleva a cabo una tarea concreta.
Ejemplos de componentes podrían ser la barra de navegación, barra lateral, marco de contenido, pie de página, etc... 

## Directivas estructurales
Son instrucciones normales que le indican a la parte del HTML qué tiene que hacer
