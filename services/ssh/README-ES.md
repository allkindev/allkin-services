# Máquina por SSH

Un servidor, un NAS, una Raspberry Pi — cualquier máquina con un servidor SSH. Los agentes a los que das este servicio ejecutan comandos allí, leen y escriben sus archivos, y nunca ven la contraseña ni la clave: se quedan en este servidor, fuera de la conversación, fuera del alcance del modelo, fuera del registro.

## La conexión

**Máquina**: su nombre o su dirección IP, con el puerto si no es el 22 (`servidor.example.com:2222`). **Cuenta**: el usuario con el que se conectan los agentes; sus derechos en esa máquina son los suyos — una cuenta propia, con solo el `sudo` que necesite, es la opción segura.

Luego una de las dos:

- **Una clave** (recomendado). Pulsa **Generar un par**: la clave pública aparece debajo, para añadirla a `~/.ssh/authorized_keys` de la cuenta en la máquina — por ejemplo `echo 'ssh-ed25519 AAAA… allkin@…' >> ~/.ssh/authorized_keys` allí. También puedes pegar una clave privada tuya, sin cifrar.
- **Una contraseña**: la de la cuenta, tal como la escribirías.

## La clave de la máquina

La primera prueba aprende la clave con la que se presenta la máquina y muestra su huella: compárala, si puedes, con `ssh-keygen -lf /etc/ssh/ssh_host_ed25519_key.pub` ejecutado en la máquina. A partir de ahí, una máquina que presente otra clave se rechaza — reinstalada, u otra máquina que responde en su dirección. Si sabes por qué cambió, **Confiar en esta clave** desde esta página.

## Lo que hacen los agentes

Tres herramientas: un comando, la lectura de un archivo, la escritura de un archivo. Cada llamada te muestra una tarjeta en el hilo — la máquina, el comando, la explicación del agente — y solo se ejecuta cuando la apruebas: una vez, para el resto de la conversación en esa máquina, o siempre, mediante un patrón guardado solo para esa máquina. **Actuar sin validación** quita la tarjeta para todos los agentes, también en una acción o una delegación, sin nadie que la vea: márcalo solo para una máquina que confiarías entera. Los comandos prohibidos en Ajustes › Agentes siguen prohibidos aquí. Cada llamada deja su línea en el registro, categoría Ordenadores.
