# SearXNG

La búsqueda web de sus agentes mediante su propio SearXNG: consulta varios
buscadores a la vez, desde su máquina, sin clave ni cuota.

## Lo que hace falta

La **integración SearXNG** de Allkin (Integraciones → Añadir → SearXNG),
instalada, con sus permisos concedidos y su servicio iniciado. Instala y
ejecuta SearXNG en la máquina por sí sola; este servicio es el camino por el
que los agentes llegan a él.

## La dirección

`http://127.0.0.1:9350` — el puerto es el **Puerto local** de los ajustes de la
integración (9350 si no lo ha cambiado). No hay ninguna clave que pegar.

## Dárselo a un agente

En la página del agente, en sus servicios, marque **SearXNG**. El agente busca
entonces en la web, las noticias, las imágenes y los vídeos mediante este
servicio.

## Cuando la prueba falla

- **Sin respuesta**: la integración no está iniciada — abra su página, conceda
  sus permisos e iníciela.
- **«not-ready»**: SearXNG aún se está instalando (unos minutos la primera vez)
  o iniciando. Espere y pruebe de nuevo.
- **Un puerto equivocado**: la dirección debe llevar el puerto de los ajustes
  de la integración.

## Conviene saber

Los buscadores rechazan a veces las peticiones de un servidor durante un rato
(un CAPTCHA, un tiempo agotado): una búsqueda vuelve entonces con menos
resultados, y dice qué buscadores no respondieron. Este servicio no se dirige a
un SearXNG instalado de otro modo: habla con la integración, que responde de
forma más corta que la API de SearXNG.
