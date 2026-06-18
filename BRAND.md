# Ventto — Manual de marca

> Tienda monoproducto · Ventilador de cuello sin aspas (bladeless) · Mercado España (B2C, ES, EUR, IVA 21% incl.)
> Documento de identidad. No se ha tocado el tema de Shopify a partir de esto.

## 1. Nombre
**Ventto** — usado de forma única y coherente en toda la tienda, copy, legal y comunicaciones.

## 2. Tagline (ES)
Propuestas:
1. **"Tu verano, en modo fresco."** ← elegida
2. "Llévate la brisa puesta."
3. "Frescor manos libres, todo el día."

**Elegida:** *Tu verano, en modo fresco.*
Motivo: corta, memorable, evoca beneficio (frescor) + control ("modo"), sin claim falso de temperatura.

## 3. Paleta de color
| Rol | Hex | Uso |
|---|---|---|
| Fondo hueso | `#F7F5F2` | Fondo general, secciones claras |
| Tinta | `#1A1A1A` | Texto principal, títulos |
| Acento cian | `#2BB6C4` | Detalles, iconos, líneas, fondos de sección |
| Coral CTA | `#FF6B5A` | Botones de acción, badges de oferta |

### Accesibilidad (WCAG AA)
- **Tinta `#1A1A1A` sobre hueso `#F7F5F2`** → contraste ≈ 16:1 ✅ (texto normal).
- ⚠️ **Texto BLANCO sobre cian `#2BB6C4`** ≈ 2.0:1 ❌ y **blanco sobre coral `#FF6B5A`** ≈ 2.6:1 ❌: NO cumplen AA para texto.
  - **Regla:** en botones coral y cian usar **texto tinta `#1A1A1A`** (coral→tinta ≈ 6.5:1 ✅, cian→tinta ≈ 7.6:1 ✅).
  - Si se exige texto blanco en CTA, usar variantes oscurecidas:
    - Coral oscuro CTA: `#D94B3B` (blanco ≈ 4.6:1 ✅).
    - Cian oscuro CTA: `#1E8A95` (blanco ≈ 4.5:1 ✅).
- El cian y el coral claros quedan reservados a fondos, iconos y elementos gráficos grandes (≥24px / bold ≥18.66px), no a texto pequeño sobre blanco.

## 4. Tipografía
- **Titulares + cuerpo:** *Plus Jakarta Sans* (sans geométrica, legible, moderna).
- **Fallback web:** *Inter*, luego system-ui sans-serif.
- Jerarquía: H1 700 / H2 600 / cuerpo 400 / CTA 600.

## 5. Voz de marca
- **Cercana y directa:** tuteo, frases cortas, cero corporativismo.
- **Honesta:** plazos de envío y beneficios reales; nunca claims de grados, ni médicos.
- **Resolutiva:** problema (calor) → solución (Ventto) en una frase.
- **Fresca con humor sutil:** ligera, veraniega, sin cursilería ni signos de exclamación en cascada.

## 6. Economía unitaria (referencia interna)
- Coste aterrizado: ~12 €/ud.
- PVP unidad: **34,95 €** (IVA incl.) · ancla `compareAtPrice` 49,95 € (solo si defendible).
- Pack 2 Ventto: **54,95 €** (vs 2×34,95 = 69,90 €) · `compareAtPrice` 69,90 €.
- Upsell correa/garantía: **4,95 €**.

## 7. Tags de gestión
Toda entidad creada lleva `dp-managed` para idempotencia y limpieza. Tags producto: `dp-managed`, `verano`, `ventilador`, `neckfan`.
