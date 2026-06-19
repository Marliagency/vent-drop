# FULFILLMENT.md — Setup de dropshipping automático (DSers + AliExpress + Stripe)

> Instrucciones para un agente Claude **con acceso a navegador** (Claude in Chrome o computer-use).
> Un agente sin navegador (como el que montó la tienda por la Admin API) NO puede hacer esto.
> Markers: **[AGENTE]** = lo hace el agente · **[TÚ]** = lo haces tú (credenciales, pagos, 2FA — nunca el agente).

---

## PROMPT LISTO PARA PEGAR (a un Claude con navegador)

```
Eres mi asistente de operaciones con acceso al navegador. Vas a dejar la tienda
Shopify "Ventto" (b2hcwr-0y.myshopify.com) con fulfillment de dropshipping
AUTOMÁTICO vía DSers + AliExpress, y la pasarela Stripe conectada.

Contexto ya hecho en la tienda:
- Producto: "Ventto — Ventilador de Cuello Sin Aspas" (variantes/SKU: VENTTO-BL Blanco,
  VENTTO-NG Negro, VENTTO-VM Verde menta) y "Pack 2 Ventto" (SKU VENTTO-PACK2).
- Producto real del proveedor (AliExpress, 8000mAh + LED):
  https://de.aliexpress.com/item/1005007528467119.html

Reglas:
- En cada paso que requiera mi login, contraseña, 2FA o datos de pago/banco, PARA y
  devuélveme el control con una instrucción clara; NO introduzcas tú esas credenciales.
- Antes de activar cualquier opción que GASTE mi dinero (auto-order), muéstrame el
  resumen y pídeme confirmación explícita.
- Trabaja paso a paso y dime al final de cada fase qué quedó hecho.
Sigue el runbook de las secciones 1 a 6 de este documento.
```

---

## 0. Requisitos que debes tener listos [TÚ]
- Cuenta de **AliExpress** con método de pago válido (tarjeta) y saldo/crédito disponible.
- Cuenta **Shopify** con permisos de admin.
- Datos para **Stripe**: razón social / autónomo, NIF, IBAN, dirección fiscal.
- Decisión de **método de envío** del proveedor (elige uno CON tracking, p.ej. AliExpress Standard / Cainiao).

## 1. Instalar DSers
1. **[AGENTE]** Abre Shopify Admin → **Apps** → busca **"DSers‑AliExpress Dropshipping"** → **Install**.
2. **[TÚ]** Acepta los permisos de la app (pantalla OAuth de Shopify).
3. **[AGENTE]** Confirma que DSers abre su panel y queda enlazado a la tienda.

## 2. Conectar AliExpress
1. **[AGENTE]** En DSers → **Settings → Account → Link to AliExpress**.
2. **[TÚ]** Inicia sesión en AliExpress y autoriza (login + 2FA los pones tú).
3. **[AGENTE]** Verifica que el estado figura como "Linked".

## 3. Importar y MAPEAR el producto
1. **[AGENTE]** En DSers usa la **importación por URL** con:
   `https://de.aliexpress.com/item/1005007528467119.html`
   (o, si instalaste la extensión DSers, "Import to DSers" desde la ficha).
2. **[AGENTE]** Ve a **My Products → Mapping** del producto Ventto:
   - Mapea **VENTTO-BL → variante Blanca** del proveedor.
   - **VENTTO-NG → Negro**, **VENTTO-VM → Verde menta**.
   - Para **Pack 2 (VENTTO-PACK2)**: mapea con cantidad **2** del mismo artículo
     (mapping avanzado/“bundle” → 2 uds) o al SKU de pack del proveedor si existe.
3. **[AGENTE]** Selecciona el **método de envío** elegido (con tracking) como predeterminado.
4. **[TÚ]** Revisa que cada variante quedó vinculada correctamente (colores/imagen coinciden).

## 4. Activar AUTOMÁTICO (auto-order + stock)
1. **[AGENTE]** DSers → **Settings → Orders → Auto Order**: prepáralo.
2. **[AGENTE]** Muéstrame el resumen (qué comprará, con qué envío, a qué coste aprox).
3. **[TÚ] CONFIRMA** antes de activar (esto hará que se gaste tu dinero solo).
4. **[AGENTE]** Activa **Auto Order: ON** tras tu confirmación.
5. **[AGENTE]** Activa **Inventory/Price Sync** (sincroniza stock real del proveedor para no
   vender sin stock). Revisa la regla de precio para no romper tu PVP (34,95 / 54,95 €).

## 5. Conectar Stripe (cobro) [TÚ]
1. Shopify Admin → **Configuración → Pagos**.
2. Activa **Shopify Payments/Stripe** → introduce **tus** datos fiscales y bancarios.
   (El agente NO mete estos datos; los pones tú.)
3. Guarda y verifica que aparece "Activo".

## 6. Prueba end-to-end (antes de lanzar de verdad)
1. **[AGENTE]** Crea un **pedido de prueba** (descuento 100% o producto de 0,01 €) o usa
   el modo test si lo activas.
2. **[AGENTE]** Verifica el flujo en DSers: el pedido entra → (auto-)order al proveedor.
   **[TÚ]** Antes de que pague de verdad, confirma o cancela según prefieras en la prueba.
3. **[AGENTE]** Comprueba que el tracking del proveedor vuelve a Shopify y al cliente.

---

## Qué queda AUTOMÁTICO tras esto
Cliente paga (Stripe) → Shopify crea el pedido → DSers lo detecta → **auto-order** compra
al proveedor con tu pago → el proveedor envía al cliente → el **tracking** se sincroniza
solo a Shopify y al email del cliente.

## Avisos honestos
- **Auto-order gasta tu dinero sin intervención**: vigila saldo/tarjeta y márgenes. Muchos
  operadores prefieren auto-order **solo hasta el paso de pago** y dar el clic final a mano
  las primeras semanas. Decide tú el nivel de automatización.
- **Stock**: sin sync, el "500" actual es ficticio. Con sync, manda el stock real del proveedor.
- **Plazos**: mantén la Política de Envíos honesta (7-15 días laborables).
- Las **imágenes** actuales son IA; cuando DSers importe, puedes sustituir la foto principal
  por la real del proveedor para fidelidad total.
