# Diseño / Tema — estado

## Moneda
- ✅ **EUR confirmado** (el widget de producto ya devuelve `currencyCode: EUR`). Precios se muestran como 34,95 € / 54,95 €.

## Tema de trabajo
- **Horizon** (`OnlineStoreTheme/193880260990`): tema EN VIVO. La Admin API bloquea escribir/publicar el tema activo, así que NO se toca.
- **Ventto — Diseño** (`OnlineStoreTheme/193881604478`, UNPUBLISHED): copia donde está el rediseño. **Publícala tú** en *Tienda online → Temas → Ventto — Diseño → Publicar*.
- Previsualizar sin publicar: *Tienda online → Temas → Ventto — Diseño → Acciones → Vista previa*.

## Cambios aplicados a la copia
- **Paleta Ventto** (`settings_data.json`): fondo hueso `#F7F5F2`, tinta `#1A1A1A`, CTA coral `#FF6B5A` con texto tinta (AA), badge oferta cian `#2BB6C4`, Plus Jakarta Sans.
- **Home** (`templates/index.json`) — 8 secciones en orden de conversión:
  1. **Hero**: "Tu verano, en modo fresco." + subtítulo (8000mAh) + CTA coral al producto.
  2. **Barra de confianza**: envío ES · pago seguro · 14 días · garantía 3 años.
  3. **Productos** (colección ventto-bestsellers, 3 col).
  4. **Beneficios** (4 tarjetas): sin aspas · 8000mAh+LED · manos libres · USB-C.
  5. **Cómo funciona** (3 pasos).
  6. **Banda garantía** (cian, ancho completo).
  7. **FAQ** (desplegables).
  8. **CTA final** coral.
- Las secciones 2/4/5/6/7/8 son `custom-liquid` (HTML/CSS propio con la paleta), robustas y sin imágenes.

## Ficha de producto
- ✅ Actualizada a **8000mAh + pantalla LED digital** (fiel al producto real del proveedor).

## Pendiente (imágenes — luego, como acordamos)
- Hero sin foto de fondo (de momento titular sobre hueso). Galería de producto vacía.
- Vías: DSers (importa fotos + fulfillment) · pegar URLs `ae01.alicdn.com` · recargar Higgsfield para IA.
