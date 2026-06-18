# Diseño / Tema — estado

## Tema de trabajo
- **Horizon** (`OnlineStoreTheme/193880260990`): tema EN VIVO. La Admin API **bloquea escribir y publicar el tema activo** por seguridad, así que NO se toca.
- **Ventto — Diseño** (`OnlineStoreTheme/193881604478`, UNPUBLISHED): copia editable donde se aplica el rediseño. **Publícala tú** desde *Tienda online → Temas → Ventto — Diseño → Publicar* cuando te convenza (la publicación por API está bloqueada).

## Cambios aplicados a la copia
- **Paleta Ventto** (`config/settings_data.json`): fondo hueso `#F7F5F2`, tinta `#1A1A1A`, **botón CTA coral `#FF6B5A` con texto tinta** (cumple AA), badge de oferta cian `#2BB6C4`, variantes/inputs/drawer en paleta de marca.
- **Tipografía**: Plus Jakarta Sans (cuerpo n4 / subtítulo n5 / títulos n7).
- **Home** (`templates/index.json`):
  - Hero: titular "Tu verano, en modo fresco." + subtítulo, texto en tinta legible sobre hueso (overlay oscuro desactivado porque no hay imagen de fondo aún), botón coral "Quiero mi Ventto" enlazado al producto.
  - Rejilla de producto apuntando a la colección **ventto-bestsellers**, 3 columnas, fondo hueso, título "Lo más fresco de Ventto", botón "Ver todos".

## Pendiente de imágenes (bloquea el hero visual y la ficha)
- Higgsfield (IA) tiene **1 crédito**; generar 1 imagen cuesta 2 → no puedo generar. Recarga créditos o pásame el enlace del proveedor / URLs https públicas.
- Con imágenes: añado foto de fondo al hero, galería de producto (Blanco/Negro/Verde menta) y fotos lifestyle. Para la ficha del producto usaré la foto REAL del proveedor (opción Mixto elegida).

## Mejoras adicionales recomendadas (cuando haya imágenes / en el editor visual)
- Secciones extra de home (beneficios en 4 columnas, "cómo funciona", garantía/envío, FAQ, opiniones): copy listo en `content/home.md`. Se añaden mejor desde el editor visual de Horizon o puedo intentarlas por API si lo pides.
