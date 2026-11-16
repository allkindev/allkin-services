# Wikipedia

Los artículos de una edición lingüística, a través de la API de MediaWiki.

## El idioma

Introduce el código de la edición: `es`, `en`, `fr`, `de`… Una conexión por
idioma; un agente que necesite dos ediciones recibe dos conexiones.

## Conviene saber

Sin clave, pero la API pide un ritmo razonable y rechaza las peticiones más
pesadas (volcado de categorías enteras). Un agente lee resúmenes, extractos y
resultados de búsqueda; no edita nada.
