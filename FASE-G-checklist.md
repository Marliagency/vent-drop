# FASE G — Checklist pre-lanzamiento Ventto

Estado a fecha 2026-06-18. Tienda: `b2hcwr-0y.myshopify.com` · Tema: Horizon (MAIN).

## Creado y verificado en Shopify

| Elemento | Estado | ID / handle |
|---|---|---|
| Producto **Ventto** (3 colores, 34,95, compareAt 49,95) | ✅ ACTIVE + publicado Tienda online/Shop | `Product/15965774545278` |
| **Pack 2 Ventto** (54,95, compareAt 69,90) | ✅ ACTIVE + publicado | `Product/15965775135102` |
| Inventario (tracked, 500/variante) | ✅ 4 variantes a 500 | Location `116388626814` |
| Colección **Ventto Bestsellers** (2 productos) | ✅ publicada | `Collection/747412750718` |
| Productos en colección `frontpage` (home) | ✅ ambos | `Collection/747411865982` |
| 6 páginas legales (ES/RGPD) | ✅ publicadas | ver `content/legal/` |
| Menú **footer** (6 legales + Contacto) | ✅ | `Menu/359913423230` |
| Menú **header** (Inicio·El Ventilador·Pack 2·Opiniones·Contacto) | ✅ | `Menu/359913390462` |
| Descuento **VERANO10** (10%, todos, activo) | ✅ activo desde 2026-06-18 | `DiscountCodeNode/2379665703294` |
| `dp-managed` / metafield `dp_managed.managed` | ✅ en productos (tag) y páginas (metafield) | — |

## ⛔ Pendiente — acciones SOLO tuyas (la web no vende sin esto)

1. **⛔ Moneda en CHF, no EUR.** La API sigue reportando `currencyCode: CHF` / país Suiza. El escaparate mostrará "CHF 34.95". Cambia en **Configuración → General** país→España y moneda→EUR. Si Shopify lo bloquea, abre ticket con soporte (la moneda principal a veces queda fijada). Los precios numéricos ya son correctos: al pasar a EUR se muestran como 34,95 € sin retocar.
2. **⛔ Contraseña de escaparate.** Las tiendas nuevas suelen tener protección por contraseña activa (no es modificable por API). Ve a **Tienda online → Preferencias → Protección con contraseña** y desactívala para que la web sea pública.
3. **⛔ Imágenes de producto.** Ventto y Pack 2 están SIN fotos. Sube a `/mnt/uploads/ventto/` o pásame URLs https públicas y las cargo (featured + galería). Sin imágenes no convierte.
4. **⛔ Pasarela de pago.** Configura un proveedor en **Configuración → Pagos**. Sin esto no se puede cobrar.
5. **⛔ Dominio propio.** Conéctalo en **Configuración → Dominios**.
6. **⛔ Datos fiscales del titular.** Rellena todos los `{{TITULAR_*}}` (ver `content/PLACEHOLDERS.md`) en las 6 páginas legales.
7. **Home (Horizon).** Pega el contenido de `content/home.md` en **Tienda online → Personalizar** (Horizon no es editable por API). La sección "Opiniones" del header apunta a `/#opiniones`; crea un bloque con ese anclaje o ajústalo.
8. **Proveedor / fulfillment.** Conecta DSers/AliExpress para tramitar pedidos.
9. **Revisión legal.** Haz revisar los textos legales con asesoría antes de vender.
10. **Reseñas.** El bloque de opiniones es placeholder; no publiques reseñas inventadas (sustituir por reales/app de reseñas).

## Upsell (FASE F) — pendiente de tu OK
- Producto "Correa de repuesto / Garantía verano 2 años" a 4,95 € `dp-managed`. Dime si lo creo.

## Placeholders `{{TITULAR_*}}`
Ver `content/PLACEHOLDERS.md`. Resumen: NOMBRE, NIF, DOMICILIO, EMAIL, TELEFONO, DOMINIO, REG_MERCANTIL, LOGISTICA, FECHA_ACTUALIZACION.

---

## Comando de limpieza `dp-managed` (NO ejecutar salvo reset)

> Borra TODO lo creado por este proceso. Revisa antes. Ejecútalo pidiéndome: "ejecuta el reset dp-managed".
> No es un único comando shell porque actúa sobre la Admin API; es la secuencia de borrado idempotente:

```
# 1. Productos con tag dp-managed (incluye Ventto, Pack 2 y futuro upsell)
search-products  query="tag:dp-managed"   -> por cada id: productDelete(id)
# 2. Colección dp-managed
collectionDelete(id: "gid://shopify/Collection/747412750718")  # Ventto Bestsellers
# 3. Páginas con metafield dp_managed.managed = true
#    handles: aviso-legal, politica-privacidad, politica-cookies,
#             condiciones-compra, politica-envios, devoluciones-desistimiento
pageDelete por cada id
# 4. Descuento
discountCodeDelete(id: "gid://shopify/DiscountCodeNode/2379665703294")  # VERANO10
# 5. Restaurar menús header/footer a su estado por defecto (manual)
```
