# OVHcloud – Dienstkonto

Domains, Hosting, dedizierte Server, VPS, Public Cloud: Die OVHcloud-API bietet
so gut wie alles, was der Manager kann.

> **Dienstkonto, nicht API-Schlüssel.** Das sind bei OVH zwei verschiedene
> Mechanismen, und die Verwechslung ist der häufigste Fehler. Die Seite
> `api.ovh.com/createToken`, auf die alle Anleitungen verweisen, liefert
> **drei** Werte und gehört zum anderen Katalogeintrag, „OVHcloud
> (API-Schlüssel)“. Ein Dienstkonto liefert **zwei**.

## Das Dienstkonto erstellen

Manager → **Identität, Sicherheit und Operationen** (Identity, security and
operations) → **Identitäten** (Identities) → **Dienstkonto** (Service account)
→ „Dienstkonto hinzufügen“ (Add a service account).

- Der **Name, den du wählst, ist die Client-ID** (Client ID).
- Das **angezeigte Passwort ist das Secret** (Client Secret); es wird nur einmal
  angezeigt.

## Der Schritt, den man vergisst und der den Agenten blind macht

Ein brandneues Dienstkonto startet **ganz ohne Ressourcen**. Die Verbindung
gelingt, der Agent fragt die API ab und bekommt leere Listen – keine Ablehnung,
sondern ein `HTTP 200` mit null Ergebnissen. Nichts weist darauf hin, dass etwas
fehlt: Es sieht aus wie ein leeres Konto.

Du musst ihm unter **Richtlinien** (Policies; gleicher Bereich des Managers)
Rechte geben: Lege eine Richtlinie an, wähle die Ressourcen und hänge das
Dienstkonto daran.

Viele hören hier auf, weil diese Oberfläche launisch ist. Wenn du nicht
durchkommst, nimm den anderen Weg: **„OVHcloud (API-Schlüssel)“** im Katalog,
dessen Rechte beim Erstellen der Schlüssel angekreuzt werden.

## Was der Agent nicht allein tut

Achtundzwanzig Aufrufmuster laufen über deine Freigabe – eine Bestellung kaufen
und bezahlen, einen Dienst kündigen, eine DNS-Zone löschen, einen Server neu
installieren. Der Agent kann sie vorbereiten und dir vorlegen; auslösen kann er
sie nicht.

Alles andere – den Katalog lesen, deine Produkte auflisten, einen Warenkorb
füllen – geht ohne Rückfrage durch.

## Gut zu wissen

- Die Standardwerte zielen auf **Europa** (`eu.api.ovh.com`). Kanadische und
  US-Konten haben ihre eigene API-Wurzel.
- Die Kontoinformationen (`/me`) werden einem Dienstkonto standardmäßig
  verweigert, während die Produkte erreichbar bleiben. Ein `403` auf `/me` ist
  also kein Zeichen für eine kaputte Einrichtung.
