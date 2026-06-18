# Proyecto: Tema Shopify — VENTTO (monoproducto, ventilador de cuello, España)

## Contexto real de este entorno (IMPORTANTE)
- El tema se edita vía **Shopify Admin API** (`themeFilesUpsert`) sobre **borradores** (no hay Shopify CLI ni `theme dev` aquí; es un agente remoto sin login local ni navegador).
- La API **bloquea escribir/publicar el tema EN VIVO**. Flujo: editar borrador → el usuario **publica a mano** desde el admin.
- **No puedo capturar screenshots** del render (escaparate con contraseña, sin navegador). El loop visual lo cierra el usuario: previsualiza y **pega una captura** para iterar.
- Tema base: **Horizon** (Online Store 2.0), no Dawn.

## Comandos / operaciones
- Editar diseño: `themeFilesUpsert` sobre el borrador activo (config/settings_data.json, templates/index.json).
- Validar GraphQL: `validate_graphql_codeblocks` (Admin) antes de mutar.
- Imágenes IA: Higgsfield modelo `soul_2` (~0,12 créd/img); URLs CloudFront públicas → se enganchan a producto/tema directamente.

## DANGER ZONES (no sin confirmación explícita)
- Publicar tema en vivo · borrar temas/secciones · tocar checkout o pagos · borrar entidades `dp-managed`.

## Reglas de trabajo
- Editar sobre borrador; el usuario publica. No publicar cada cambio: acumular y publicar una vez.
- Secciones de contenido propias vía `custom-liquid` (HTML/CSS) para no romper el schema de bloques de Horizon.
- Mobile-first, foco visible, `prefers-reduced-motion` respetado, contraste AA.
- Nada de claims falsos; plazos de envío honestos.

## DESIGN TOKENS — "flujo térmico" (calor -> frescor)
- --ink #11181C · --bg #F4F7F8 · --bg-2 #FFFFFF
- --cool #14B8C6 · --cool-deep #0E8F9E (marca/frescor)
- --heat #FF5A4D (solo CTAs/acentos) · --muted #5B6B72
- Tipografía: Display "Clash Display", Body "General Sans", Datos "Space Mono" (Fontshare, vía @font-face en secciones custom).

## Signature
Hero "flujo de aire": gradiente calor->frescor + líneas SVG animadas (con reduced-motion). La audacia va en el hero; el resto sobrio.

## Anti-patrones
No crema+serif+terracota. No negro puro+acid green. No periódico hairline radius 0. No carruseles genéricos.
