# Stories y documentación

En la libreria de componentes utilizamos una herramienta llamada [storybook](https://storybook.js.org) que nos permite visualizar los componentes desarrollados de manera aislada. Esto facilita su documentación e implementación, ya que permite hacer pruebas si necesidad de implementarlo en un proyecto con todo lo que implica.

Para crear una storie para un componente:

1. Crear un archivo con la nomenclatura establecida, esta es: 
   - nombre del componente + stories + extensión. Ej: `alert.component.ts`
2. Crear la estructura base dentro del archivo:
```js
import { moduleMetadata, storiesOf } from '@storybook/angular';   
import { KuiComponent } from './kui.component';  
import { withA11y } from '@storybook/addon-a11y';

//documentation
const documentation = require('./alert.doc.md');  
  
const stories = storiesOf('Components | System notifications/Kui Component', module);  
  
stories.addDecorator(withAlly).addDecorator(  
    moduleMetadata({  
        declarations: [KuiComponent],  
        imports: []  
    }));

stories.add(  
    'First casuistica',  
    () => ({        component: AlertComponent,  
        template: `<kui-component [input] = "type 2" ></kui-component>`    
        }),  
    { notes: documentation.default }  
);

stories.add(  
    'Second casuistica',  
    () => ({        component: AlertComponent,  
        template: `<kui-component [input] = "type 2"></kui-component>`    
        }),  
    { notes: documentation.default }  
);
```

3. Armar las stories importando todo lo necesario para que funcione el componente. Cada una de los stories debe abarcar los diferentes casuísticas del componente.

_Nota: Usar como ejemplo las stories ya desarrolladas en la kui, ya que no usamos la ultima versión de storybook y parte de la documetacion correspondiente a nuestra version ya no se encuentra disponible._

4. Armar un archivo de documetación del componente que despues ser verá en las stories. Este archivo tiene que seguir la estructura establecida en el archivo base.doc.md que se encuentra dentro de la libreria.
   
   El archivo de documetacion debe tener el sigueinte formato.
   - nombre del componente + doc + md. Ej: `alert.dos.md`
