# Stripe

Pagos, clientes, facturas, suscripciones, reembolsos, enlaces de pago.

## La clave

**<https://dashboard.stripe.com/apikeys>**. Prefiere una **clave restringida** con solo los permisos que necesita el agente, y empieza con la clave del **modo de prueba** (`sk_test_…`): con ella no se mueve nada real.

## Conviene saber

Todo lo que mueve dinero (reembolsos, cobros, transferencias, pago de una factura, suscripciones) pide tu confirmación, igual que eliminar. Los importes están en la unidad más pequeña (céntimos).
