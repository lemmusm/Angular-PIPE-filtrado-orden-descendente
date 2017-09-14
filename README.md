# Angular PIPE (filtrado orden descendente)
Creado con el objetivo de ordenar una lista de forma descendente mediante el uso de pipes en *ngFor

## Creamos un nuevo archivo typescript (.ts) para el nuevo pipe y agregamos lo siguiente:

```
import { Pipe, PipeTransform } from '@angular/core';

@Pipe({
  name: 'reverse'
})
export class ReversePipe implements PipeTransform {
  transform(value) {
    if (!value) return;

    return value.reverse();
  }
}
```

## Agregamos el pipe a nuestro app.module.ts

```
  import {ReversePipe} from 'path-to-source';
  
  @NgModule({
  declarations: [
    AppComponent,
    ReversePipe
  ]
```
## Por último lo importamos a nuestro componente dentro del archivo .ts y dentro del .html hacemos uso del pipe mediante *ngFor

```
component.ts

import {ReversePipe} from 'path-to-source';
  
  ```
  
  ```
component.html

*ngFor="let item of items | async | reverse;"
  
  ```
