# Telegram

Un canal de salida: el agente envía mensajes, no recibe ninguno.

## Crear el bot

Escribe a **@BotFather** en Telegram, comando `/newbot`. Te devuelve un token
con la forma `123456789:AAE...`.

## El identificador de la conversación

Es el campo más importante, y el único que exige un paso manual.

1. Envía un mensaje a tu bot (o añádelo a un grupo y escribe en él).
2. Abre `https://api.telegram.org/bot<YOUR_TOKEN>/getUpdates`.
3. Lee `chat.id`: **negativo** para un grupo, positivo para una conversación
   directa.

## Por qué este campo es obligatorio

Una clave de bot de Telegram puede escribir en **cualquier** conversación que el
bot conozca. El identificador que introduces aquí lo reescribe Allkin en cada
llamada, pasando por encima de lo que haya puesto el agente.

Dicho de otro modo: no es una indicación, es una restricción. El bot solo podrá
escribir en esta conversación, pida lo que pida un agente.

## Conviene saber

El botón «Enviar un mensaje de prueba» de la ficha del servicio envía un mensaje
real. Es la única forma de comprobar el destino: una clave válida no demuestra
que el mensaje llegue al lugar correcto.
