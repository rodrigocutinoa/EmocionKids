# 🐾 FerretHappy

Aplicación para identificar el estrés emocional en alumnos de 5 a 12 años.

## Publicar en GitHub Pages

1. Sube esta carpeta a un repositorio de GitHub
2. Ve a **Settings → Pages**
3. En "Source" selecciona la rama `main` y carpeta `/ (root)`
4. Haz clic en **Save**
5. En unos minutos tu app estará en: `https://TU-USUARIO.github.io/NOMBRE-REPO/`

## Estructura de archivos

```
ferrethappy/
├── index.html   ← Página principal (GitHub Pages la busca aquí)
├── styles.css   ← Todos los estilos visuales
├── app.js       ← Toda la lógica de la aplicación
└── README.md    ← Este archivo
```

## Descripción de cada archivo

### `index.html`
El punto de entrada de la aplicación. Contiene solo el esqueleto HTML:
- Importa `styles.css` para los estilos
- Importa `app.js` para la lógica
- Tiene un `<div id="app">` donde se renderiza todo dinámicamente
- **Debe estar en la raíz** para que GitHub Pages lo detecte automáticamente

### `styles.css`
Contiene todo el diseño visual de la app:
- Variables de colores pasteles (lavanda, menta, melocotón, cielo)
- Estilos de tarjetas, botones, tablas y animaciones
- Diseño responsive para PC y celular
- Estilos específicos para la tabla de alumnos, caritas emocionales y perfil de alumno/docente

### `app.js`
Toda la lógica de la aplicación en JavaScript puro (sin frameworks):
- **Fotos embebidas en Base64**: Las imágenes de Blue (alumno) y la huroncita docente están codificadas directamente en el archivo, por eso no necesita carpeta de imágenes
- **Constante `FERRET`**: Objeto con los métodos `photo()` (foto real de Blue) y `teacher` (foto docente), más SVGs decorativos de hurón para otras pantallas
- **Constante `EMOTIONS`**: Define las 3 caritas (Triste, No sé, Contento) con sus SVGs y colores
- **Constante `CATEGORIES`**: Las 3 categorías de encuesta (Colegio, Amigos, Familia)
- **Estado global `state`**: Guarda el perfil activo, respuestas del alumno actual y lista de todos los alumnos encuestados
- **Flujo Alumno**: `screenAlumnoWelcome` → `screenAlumnoNombre` → `screenAlumnoCategoria` (×3) → `screenAlumnoResultado` → `screenFinOrOtro`
- **Flujo Docente**: `screenDocenteWelcome` → `screenDocenteOpciones` → `screenDocenteResumen` o `screenDocenteLista`
- **Función `grabarHTML`**: Genera y descarga automáticamente un reporte HTML con los resultados de todas las encuestas del día
