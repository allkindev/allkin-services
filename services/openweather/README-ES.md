# OpenWeather

Tiempo actual y previsiones.

## La clave

**<https://openweathermap.org>** → tu cuenta → **API keys**.

Una clave nueva tarda **hasta dos horas** en activarse. Un `401` justo después
de registrarte no es, por tanto, un error al teclear: es demasiado pronto.

## Conviene saber

El nivel gratuito cubre el tiempo actual y las previsiones a cinco días, hasta
sesenta llamadas por minuto. Las API «One Call» e históricas exigen una
suscripción: un agente que recibe un `401` en ellas tiene una clave válida pero
el plan equivocado.
