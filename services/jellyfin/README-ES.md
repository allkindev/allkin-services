# Jellyfin

Tu mediateca: bibliotecas, películas, series, lo que se está reproduciendo.

## La clave

**Panel de control** → **Avanzado** → **Claves API** → **+**.

## La URL base

La dirección de tu servidor, tal como la abrirías en un navegador:

```
https://media.example.com        ✅
http://192.168.1.30:8096         ✅
```

Sin barra final. Allkin la quita de todos modos, pero conviene saberlo: esa
barra es la que produce los `//` y los 404 cuando pegas la dirección desde la
barra del navegador.

## Conviene saber

Una clave API de Jellyfin tiene permisos de administrador: ve todas las
bibliotecas y todos los usuarios. No existe una clave restringida.
