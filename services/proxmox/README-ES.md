# Proxmox VE

Máquinas virtuales, contenedores, nodos, almacenamiento, tareas.

## El token

**Datacenter → Permissions → API Tokens → Add**: elige el usuario, da un
identificador al token y deja **Privilege Separation** marcado para que sus
permisos se fijen aparte. Luego **Permissions → Add → API Token Permission**
sobre las rutas que puede tocar (`/` con `PVEAuditor` para leer, `PVEVMAdmin`
para actuar sobre las VM).

Introduce la clave como `usuario@realm!token=secreto`, de una pieza, tal como
Proxmox la muestra una sola vez. La dirección es `https://host:8006`.

## Conviene saber

Proxmox viene con un certificado autofirmado: Allkin lo rechaza. Pon un
certificado real en el nodo, o pasa por un proxy inverso que lo tenga.
Detener, reiniciar y eliminar piden tu confirmación.
