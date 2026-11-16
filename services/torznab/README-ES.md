# Torznab

El estándar de consulta de indexadores: Prowlarr, Jackett y la mayoría de los
trackers que exponen una API de búsqueda.

## La URL base

Es la **dirección exacta de la API**, no el nombre de dominio del sitio. Una API
Torznab no tiene ruta: todo ocurre en los parámetros de consulta, y la dirección
que das se llama tal cual.

```
https://mysite.org/api           ✅
https://mysite.org               ❌ you will get the site's home page
```

La prueba lo comprueba: envía `?t=caps` (la única petición que el estándar exige
a todo indexador) y rechaza una respuesta que no sea Torznab. Una página web ya
no pasa por una API.

Dónde encontrar la dirección:

- **Indexador público**: tu página de perfil, junto a la clave.
- **Prowlarr**: botón «Copy Torznab Url» en el indexador; clave en
  Settings → General.
- **Jackett**: botón «Copy Torznab Feed»; clave en la parte superior del panel.

Suele terminar en `/api`, a veces en algo como
`/api/v2.0/indexers/…/results/torznab`.

## Lo que el agente hace con ella

Empieza siempre por `?t=caps`, que le dice qué búsquedas y qué categorías acepta
el indexador; varía de uno a otro. Después `?t=search&q=…`, `?t=tvsearch`,
`?t=movie`.

El indexador responde en XML; **Allkin lo convierte a JSON** antes de
entregárselo al agente. No es por comodidad: es lo que permite al agente extraer
solo lo que quiere. Una búsqueda de veinticinco resultados pesa más de 20 000
caracteres, y lo que entra en una conversación se vuelve a pagar en cada turno
posterior. Si se piden solo los títulos, la misma búsqueda se queda en 1200.

Cada resultado lleva un enlace de descarga que el agente guarda directamente en
sus archivos, como `.torrent`.

## Tu clave no llega al contexto

Muchos indexadores repiten la clave sin cifrar en el enlace de descarga de
**cada** resultado. Una sola búsqueda la dejaría decenas de veces en la
conversación del agente, donde se quedaría.

Allkin la sustituye antes de que la respuesta llegue al modelo. Medido en una
búsqueda real: veinticinco apariciones enmascaradas, ninguna sin cifrar.
