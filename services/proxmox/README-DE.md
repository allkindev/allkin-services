# Proxmox VE

Virtuelle Maschinen, Container, Knoten, Speicher, Aufgaben.

## Das Token

**Datacenter → Permissions → API Tokens → Add**: Benutzer wählen, dem Token
eine Id geben und **Privilege Separation** aktiviert lassen, damit seine Rechte
getrennt gesetzt werden. Dann **Permissions → Add → API Token Permission** auf
den Pfaden, die es berühren darf (`/` mit `PVEAuditor` zum Lesen, `PVEVMAdmin`
zum Steuern von VMs).

Den Schlüssel als `benutzer@realm!token=geheimnis` eingeben, in einem Stück,
genau wie Proxmox ihn einmalig anzeigt. Die Adresse ist `https://host:8006`.

## Gut zu wissen

Proxmox kommt mit einem selbstsignierten Zertifikat: Allkin lehnt es ab. Ein
echtes Zertifikat auf den Knoten legen oder über einen Reverse-Proxy gehen, der
eines hat. Stoppen, Neustarten und Löschen fragen nach deiner Bestätigung.
