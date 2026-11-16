# Cloudflare Workers AI

Genera imágenes para tus agentes, **gratis** dentro de una asignación diaria que
ofrece Cloudflare (del orden de unos cientos de imágenes al día con FLUX
schnell). Más allá, las llamadas fallan hasta el día siguiente: no se factura
nada mientras tu cuenta siga en la oferta gratuita.

## Qué necesitas

1. Una cuenta gratuita de Cloudflare: <https://dash.cloudflare.com/sign-up>.
2. Tu **Account ID**: en el panel, abre **AI › Workers AI**. Aparece a la
   derecha (32 caracteres hexadecimales).
3. Un **token de API**: en **Workers AI**, botón **Use REST API › Create a
   Workers AI API Token**. La plantilla de token que propone da exactamente los
   permisos necesarios (Workers AI: lectura y edición). Cópialo: solo se
   muestra una vez.

## En Allkin

- Pega aquí el Account ID y el token, y luego **Probar**.
- En la ficha de este servicio, bajo **Lo que este servicio hace para los agentes**, activa
  **Generación de imágenes** (y la voz o la transcripción si las quieres) y elige el modelo.
- En la página de un agente, bajo **Servicios**, autoriza este servicio: el agente tiene las herramientas.

Las imágenes se guardan en la carpeta `images/` del agente y se muestran en la
conversación.

## Modelos

| Modelo | Para qué |
| --- | --- |
| `@cf/black-forest-labs/flux-1-schnell` | El mejor resultado, formato cuadrado. Por defecto. |
| `@cf/bytedance/stable-diffusion-xl-lightning` | Muy rápido, formatos vertical y horizontal. |
| `@cf/lykon/dreamshaper-8-lcm` | Estilo ilustración, rápido. |

Tus prompts salen hacia Cloudflare: no pongas en ellos nada confidencial.
