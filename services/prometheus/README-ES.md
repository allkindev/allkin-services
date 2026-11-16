# Prometheus

Métricas y consultas PromQL, instantáneas o sobre un rango.

## Nada que introducir

Prometheus no tiene autenticación propia: basta con la dirección. Si el tuyo
está detrás de un proxy inverso con contraseña, usa la entrada genérica
«cualquier API con clave».

## Conviene saber

Una consulta sobre un rango puede devolver mucho: el agente mantiene rangos
cortos y pasos amplios. La página de objetivos dice qué exportadores responden.
