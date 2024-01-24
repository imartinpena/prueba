# prueba
Hola Mundo
añadir pagina estatica

Crear una página estática en el contexto de una aplicación Node.js con Express generalmente implica servir archivos HTML, CSS y JavaScript sin realizar procesamiento adicional en el servidor. Aquí te muestro cómo puedes hacer esto:

### 1. Crear el Archivo HTML

Primero, crea un archivo HTML. Puedes llamarlo `static-page.html`. Colócalo en una carpeta llamada `public` en la raíz de tu proyecto `ejemploLogin` (si no existe, créala).

```html
<!-- static-page.html -->
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Página Estática</title>
    <link rel="stylesheet" href="/stylesheets/style.css"> <!-- Asegúrate de que este path sea correcto -->
</head>
<body>
    <h1>Bienvenido a la Página Estática</h1>
    <p>Esta es una página estática en tu aplicación Express.</p>
    <!-- Agrega más contenido HTML según sea necesario -->
</body>
</html>
```

### 2. Servir Archivos Estáticos en Express

Express puede servir archivos estáticos como HTML, CSS y JavaScript desde una carpeta en tu aplicación. Para hacer esto, usa el middleware `express.static`. 

En tu archivo `app.js` (o donde configures tu aplicación Express), asegúrate de tener una línea que sirva los archivos estáticos desde la carpeta `public`.

```javascript
const express = require('express');
const app = express();
const path = require('path');

// ... otras configuraciones ...

// Servir archivos estáticos
app.use(express.static(path.join(__dirname, 'public')));

// ... tus rutas, manejo de errores, etc. ...
```

### 3. Acceder a la Página Estática

Con esta configuración, deberías poder acceder a tu página estática a través de la URL correspondiente al archivo en tu navegador. Por ejemplo, si tu archivo se llama `static-page.html` y está en la carpeta `public`, puedes acceder a él en:

```
http://localhost:3000/static-page.html
```

(Reemplaza `3000` con tu número de puerto si es diferente).

Con estos pasos, has creado una página estática simple y configurado tu aplicación Express para servirla. Puedes personalizar el contenido HTML según tus necesidades y agregar más archivos estáticos según sea necesario.
