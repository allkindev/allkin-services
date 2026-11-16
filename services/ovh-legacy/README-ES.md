# OVHcloud: claves de API

El método histórico de OVH: tres claves y una firma por petición.

**Es el camino que hay que tomar si quieres que el agente pueda hacer pedidos.**
Comprobado en una cuenta real: estas claves sortean el IAM allí donde una cuenta
de servicio se topa con él. Actúan con la identidad de la propia cuenta, con el
rol ADMIN, y no con una identidad nueva sin permisos.

## Crear las claves

Abre **<https://api.ovh.com/createToken/>**, con la sesión iniciada en tu
cuenta.

| Campo | Valor |
| --- | --- |
| Script name | `allkin` |
| Validity | Unlimited |
| Rights | el mínimo útil |

Sobre los permisos: `GET` en `/*` basta para un agente que lee. Añade `POST`,
`PUT` y `DELETE` en `/*` solo si el agente tiene que escribir: **esos permisos
valen para toda tu cuenta**, sin distinción entre productos.

La página devuelve entonces **tres valores**, que hay que introducir en los tres
campos de la pestaña «Servicio». Solo se muestran una vez.

## Lo que das a cambio

Ninguna política IAM que crear: los permisos que marcas son efectivos desde la
primera petición. Ese es todo el interés de este camino.

A cambio, estas claves son amplias. Lo que acota al agente aquí no es OVH: es
Allkin, que intercepta la compra, el pago, la baja y la eliminación y te los
somete. Aun así, restringe los patrones en lugar de marcarlo todo: una
salvaguarda vale más cuando no es la única.

## Conviene saber

Allkin calcula la firma en cada llamada, sobre el método, la URL y el cuerpo. El
secreto de aplicación (Application Secret) nunca sale de la máquina: solo sirve
para calcular el hash.
