# Paperless-ngx

Tus documentos: búsqueda de texto completo, etiquetas, remitentes, tipos.

## El token

**Perfil (arriba a la derecha) → Token de autenticación API → generar**. O en
la máquina: `manage.py drf_create_token <usuario>`. La dirección es la de la
interfaz web.

## Conviene saber

Las rutas terminan en barra, la API está paginada (25 por defecto). Eliminar
un documento pide tu confirmación; la papelera lo conserva un tiempo de todos
modos.
