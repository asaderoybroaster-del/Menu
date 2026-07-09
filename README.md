# Menú Interactivo — Asadero y Broaster a Fuego Lento

Menú digital, 100% front-end (HTML + CSS + JavaScript puro, sin frameworks ni build step).

## Cómo usarlo

1. Descomprime el .zip.
2. Abre `index.html` haciendo doble clic (funciona directamente en el navegador, sin servidor).
   - Si prefieres verlo con un servidor local: `python3 -m http.server` dentro de la carpeta y entra a `http://localhost:8000`.
3. Sube la carpeta completa (con `assets/`) a cualquier hosting estático si quieres publicarlo: GitHub Pages, Netlify, Vercel, o el hosting que ya tengas.

## Estructura

```
menu-project/
├── index.html      ← toda la página (HTML + CSS + JS en un solo archivo)
├── assets/         ← fotos recortadas del menú original
└── README.md
```

## Cómo funciona la navegación

- El menú completo está en el objeto `MENU` dentro de `index.html` (dentro de la etiqueta `<script>`), organizado por secciones: `combos`, `broaster`, `carta`, `parrilla`, `entradas`, `bebidas`.
- Los botones de arriba (nav) se generan automáticamente a partir de ese objeto. Al hacer clic en "Combos" se muestra solo esa sección; al hacer clic en "Bebidas" se muestra solo bebidas, etc. — es un cambio de vista instantáneo (SPA), no recarga la página.
- También soporta enlaces directos: `index.html#bebidas` abre el menú ya en la pestaña de Bebidas.

## Cómo editar precios o platos

Todo el contenido (nombres, precios, descripciones, imágenes) vive en el objeto `MENU` al inicio del `<script>`. Por ejemplo, para cambiar el precio de un combo:

```js
{ name:"Combo 1", price:"52.000", tag:"1 Pollo Asado", desc:"...", img:"assets/icon_combo1.png"},
```

Solo cambia el valor de `price` (o `desc`, `name`, etc.) y guarda — no necesitas tocar el HTML ni el CSS.

## Cómo agregar una foto nueva

1. Copia tu imagen dentro de `assets/`.
2. Referencia la ruta en el ítem correspondiente del objeto `MENU`, ej: `img:"assets/mi_foto.png"`.

## Notas

- Las fotos de los platos fueron recortadas directamente de la imagen del menú original que enviaste, para que coincidan exactamente con tu marca.
- Todos los textos y precios fueron transcritos tal como aparecen en la imagen original.
