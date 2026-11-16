# OpenWeather

Aktuelles Wetter und Vorhersagen.

## Der Schlüssel

**<https://openweathermap.org>** → dein Konto → **API keys**.

Ein neuer Schlüssel braucht **bis zu zwei Stunden**, bis er aktiv ist. Ein `401`
direkt nach der Anmeldung ist also kein Tippfehler: Es ist zu früh.

## Gut zu wissen

Die kostenlose Stufe deckt das aktuelle Wetter und die Fünf-Tage-Vorhersagen ab,
bis zu sechzig Aufrufe pro Minute. Die „One Call“-API und die historischen APIs
verlangen ein Abo – ein Agent, der dort ein `401` bekommt, hat einen gültigen
Schlüssel, aber den falschen Tarif.
