# Portal académico — páginas individuales

## Contenido
- `index.html`: portada con **8 unidades de aprendizaje** y biblioteca.
- `cursos/*.html`: una página estática para cada asignatura.
- `cursos/estilos-curso.css`: diseño adaptable.
- `cursos/curso.js`: visor de documentos PDF.
- `materiales/`: incluye el PDF de IA previamente proporcionado, si estaba disponible.

## Publicación en GitHub Pages
1. Extrae el ZIP.
2. Sube **todo el contenido interior** a la raíz de tu repositorio, manteniendo la estructura.
3. En Settings → Pages elige main y /(root).
4. Las tarjetas de la portada abren las páginas de `cursos/`.

## Añadir materiales a la página de una materia
1. Sube el PDF a `materiales/<materia>/archivo.pdf` desde GitHub.
2. Abre la página correspondiente, por ejemplo `cursos/sensores-actuadores.html`.
3. Dentro de `<section id="diapositivas">`, antes de `<iframe ...>`, agrega:

```html
<article class="file">
  <div><strong>Clase 01 — Introducción</strong><small>Unidad 1 · Presentación</small></div>
  <div class="actions">
    <button class="btn" type="button" data-pdf="../materiales/sensores/Clase01.pdf">Ver PDF</button>
    <a class="btn secondary" href="../materiales/sensores/Clase01.pdf" target="_blank" rel="noopener">Abrir archivo</a>
  </div>
</article>
```

**IMPORTANTE:** usa `../materiales/` porque estas páginas están dentro de `cursos/`. El archivo PDF debe existir con exactamente el mismo nombre (mayúsculas incluidas).

## Añadir una nueva asignatura
Crea `cursos/nueva-materia.html` copiando una página existente, actualiza su contenido y agrega en la portada la materia y su enlace. Para evitar errores, no sustituyas el resto de las materias ni borres llaves y comas de la lista.

**Nota:** los contenidos de las páginas son propuestas orientativas y no sustituyen programas analíticos oficiales. Las listas de recursos que se añadan solo a la página individual no se incorporan automáticamente al contador de recursos de la portada; para eso también debes actualizar la entrada correspondiente en el arreglo `resources` de `index.html`.
