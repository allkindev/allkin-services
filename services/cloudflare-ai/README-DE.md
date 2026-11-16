# Cloudflare Workers AI

Erzeugt Bilder für deine Agenten, **kostenlos** im Rahmen eines Tageskontingents,
das Cloudflare gewährt (in der Größenordnung von einigen hundert Bildern pro Tag
mit FLUX schnell). Darüber hinaus schlagen die Aufrufe bis zum nächsten Tag
fehl: Nichts wird berechnet, solange dein Konto im kostenlosen Tarif bleibt.

## Was du brauchst

1. Ein kostenloses Cloudflare-Konto: <https://dash.cloudflare.com/sign-up>.
2. Deine **Account ID**: Öffne im Dashboard **AI › Workers AI**. Sie steht
   rechts (32 hexadezimale Zeichen).
3. Ein **API-Token**: in **Workers AI**, Schaltfläche **Use REST API › Create a
   Workers AI API Token**. Die vorgeschlagene Token-Vorlage gibt genau die
   nötigen Rechte (Workers AI: lesen und bearbeiten). Kopiere es: Es wird nur
   einmal angezeigt.

## In Allkin

- Füge die Account ID und das Token hier ein, dann **Testen**.
- Schalte auf der Seite dieses Dienstes unter **Was dieser Dienst für die Agenten tut** die
  **Bilderzeugung** ein (und Stimme oder Transkription, wenn du sie willst) und wähle das Modell.
- Erlaube den Dienst auf der Seite eines Agenten unter **Dienste**: der Agent hat die Werkzeuge.

Die Bilder liegen im Ordner `images/` des Agenten und erscheinen in der
Unterhaltung.

## Modelle

| Modell | Wofür |
| --- | --- |
| `@cf/black-forest-labs/flux-1-schnell` | Das beste Ergebnis, quadratisches Format. Standard. |
| `@cf/bytedance/stable-diffusion-xl-lightning` | Sehr schnell, Hoch- und Querformat. |
| `@cf/lykon/dreamshaper-8-lcm` | Illustrationsstil, schnell. |

Deine Prompts gehen an Cloudflare: Schreib nichts Vertrauliches hinein.
