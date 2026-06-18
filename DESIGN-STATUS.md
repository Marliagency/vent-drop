# Diseño / Tema — estado

## Moneda
- ✅ **EUR confirmado** (el widget de producto ya devuelve `currencyCode: EUR`). Precios se muestran como 34,95 € / 54,95 €.

## Temas (la API solo deja editar borradores; tú publicas)
- **Ventto — Diseño** (`193881604478`): **EN VIVO** (lo publicaste). Tiene paleta + home de 8 secciones.
- **Ventto — Diseño v2** (`193893859710`, borrador): **versión mejorada** con hero de degradado + tabla comparativa. **Publícala tú** para que sea la nueva home: *Tienda online → Temas → v2 → Publicar*. Previsualiza antes en *Acciones → Vista previa*.
- **Horizon** (`193880260990`): borrador original de respaldo.
- Nota: cada vez que publicas un tema, la API ya no puede editarlo (bloqueo del tema en vivo); por eso para cada mejora creo un borrador nuevo (vN) y lo publicas tú. Puedes borrar los temas antiguos a mano para no acumular.

## Pase de diseño v2 (en el borrador v2)
- **Hero premium**: degradado suave cian→hueso, etiqueta superior, titular grande responsive, doble CTA (coral + contorno a Pack 2) y microcopia de confianza.
- **Tabla comparativa** "Ventto vs. ventilador normal" (columna Ventto resaltada en cian).
- Tarjetas de beneficios/FAQ con borde sutil para más definición.

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
