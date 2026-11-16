# Soniox

Transcripción de voz, en directo y sobre archivos grabados, con separación de interlocutores. Se factura por hora de audio.

## La clave

**<https://console.soniox.com>** → un proyecto → **API Keys → Create API key**.

## Conviene saber

Un proyecto de Soniox vive en **una región**, y su clave solo funciona allí. La dirección que aparece es la de Estados Unidos; para un proyecto creado en otra región, sustitúyala por `https://api.eu.soniox.com` (Unión Europea), `https://api.jp.soniox.com` (Japón) o `https://api.in.soniox.com` (India). Una clave usada contra la región equivocada se rechaza como una clave falsa.

La escucha de un micrófono pasa por el plugin **Recordr**: elija este servicio en sus ajustes. El audio va entonces del navegador directamente a Soniox, con una clave que vive dos minutos; la clave real se queda en Allkin.

Un agente al que se concede este servicio puede transcribir una grabación accesible por URL. Un archivo del disco del agente no puede enviarse por este relé.
