# Anderer OAuth2-Dienst

Der Eintrag für einen Dienst, der sich per OAuth2 authentifiziert, aber nicht im
Katalog steht.

## Was einzutragen ist

- **Autorisierungs-URL** und **Token-URL** – die beiden OAuth2-Endpunkte des
  Dienstes, aus seiner Dokumentation.
- **Client ID** und **Client Secret** – du bekommst sie, indem du dort eine
  Anwendung registrierst.
- **Berechtigungsumfänge** – durch Leerzeichen getrennt.

## Die Weiterleitungs-URI

Die Adresse, die im Tab „Dienst“ steht, muss **exakt** in die Konfiguration der
Anwendung beim Anbieter übernommen werden. Das ist die fast immer zutreffende
Ursache für abgelehnte Verbindungen: ein anderer Port, ein Schrägstrich zu viel
am Ende, und die Autorisierung wird abgelehnt.

## Gut zu wissen

Dieser Eintrag setzt den Ablauf „im Namen eines Nutzers“ voraus: eine
Schaltfläche „Verbinden“, eine Weiterleitung, eine Rückkehr. Ein Dienst, der
sich selbst authentifiziert – Dienstkonto, `client_credentials` –, wird nicht
hier eingerichtet; er braucht einen eigenen Katalogeintrag, wie OVHcloud.
