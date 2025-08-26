# MDC Digital — Cotizador

Cotizador web estático (HTML/CSS/JS) para generar cotizaciones en PDF:
- Catálogo por marcas y categorías, con imágenes.
- Carrito con descuento e IVA fijo (MXN) y modo internacional (USD sin IVA).
- Financiamiento: 12/24/36/48 meses con interés (APR 22%) y opción **1/3 enganche + 12 MSI (0%)**.
- PDF con productos (imagen opcional), totales y plan financiero.

## Estructura
```
public/
  index.html
  logo-mdc.png
  mdc digital color.png
  images/
    brands/*.png
    products/*.png
```

## Desarrollo local
Abre un servidor estático para evitar problemas de CORS de imágenes al exportar PDF:
```bash
npx serve public -p 5173
# o
npx http-server public -p 5173 --cors
```
Luego visita: http://localhost:5173

## Deploy en Netlify
- Build command: *(vacío)*
- Publish directory: `public`

## Personalización rápida
- **Tasa**: `APR = 22` (JS).
- **IVA**: `IVA_PCT = 16` (fijo).
- **Tipo de cambio**: editable en UI (modo internacional).
- **Folio**: autoincrementa por mes (usa `localStorage`).

## Imágenes
- Marcas (UI): `public/images/brands/<marca>.png`
- Productos: `public/images/products/<SKU>.png`  
  También puedes añadir `"image": "URL"` por ítem en el JSON embebido.
