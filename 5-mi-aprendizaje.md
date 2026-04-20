# Mi aprendizaje
En esta segunda práctica realicé la configuración de entornos más completos utilizando variables de entorno, redes y la integración de múltiples contenedore sn Docker. También reforcé el uso de comandos para la creación y administración de contenedores, así como la importancia de definir correctamente los parámetros al momento de ejecutarlos. Entendí que pequeños errores en la configuración, como nombres de red incorrectos o variables mal definidas, pueden provocar fallos en el funcionamiento de las aplicaciones.

### Conocimientos previos
- Creación de contenedores, descarga de imagen y eliminación de contenedores o imagenes.
- Uso de imágenes y comandos fundamentales como docker run, docker ps y docker rm.
- Mapeo de puertos para la visualización al contenedor y su información.

### Conocimientos adquiridos después de la práctica
- Configuración de contenedores utilizando variables de entorno para definir parámetros como usuarios, contraseñas y bases de datos.
- Creación de redes en Docker, permitiendo la comunicación entre contenedores.
- Integración de servicios, como WordPress y MySQL, para formar aplicaciones completas.
- Comprensión de la persistencia de datos, identificando que la información se almacena en la base de datos y no en el contenedor.
- Uso de comandos como docker logs y docker inspect para verificar configuraciones.

### Comandos
- **docker run -d --name `<nombre_contenedor>` -e `<variable>=<valor>` `<imagen>`:**  
  Permite crear un contenedor en segundo plano definiendo variables de entorno.

- **docker network create `<nombre_red>` -d bridge:**  
  Crea una red de tipo bridge para la comunicación entre contenedores.

- **docker run -d --name `<nombre_contenedor>` --network `<nombre_red>` `<imagen>`:**  
  Crea un contenedor y lo conecta directamente a una red específica.

- **docker network inspect `<nombre_red>`:**  
  Muestra información detallada de una red, incluyendo los contenedores conectados.

- **docker network connect `<nombre_red>` `<nombre_contenedor>`:**  
  Conecta un contenedor a una red existente.

- **docker network disconnect `<nombre_red>` `<nombre_contenedor>`:**  
  Desconecta un contenedor de una red.

- **docker network ls:**  
  Lista todas las redes disponibles en Docker.

- **docker network rm `<nombre_red>`:**  
  Elimina una red existente.

## Problema al usar variables de entorno en Docker

Al ejecutar el siguiente comando:

docker run -d --name `<nombre_contenedor>` `<imagen>` -e `<variable1>=<valor1>`

Durante la práctica, el contenedor no se creaba correctamente y se generaban errores en la ejecución. El error ocurrió porque se colocó incorrectamente la imagen antes de definir las variables de entorno. En Docker, todas las opciones deben ir antes del nombre de la imagen.

**Problema** 

docker run -d --name `<nombre_contenedor>` `<imagen>` -e `<variable1>=<valor1>`

Se corrigió el orden del comando, colocando primero las opciones y luego la imagen. Por lo que, se aprendió que primero van las opciones (-d, --name, -e, -p) y al final siempre va el nombre de la imagen.

### Cosas que realicé y aprendí
- Aprendí a definir variables como usuarios, contraseñas y nombres de bases de datos al momento de crear contenedores, lo cual es fundamental para la correcta inicialización de servicios como MySQL y WordPress. También comprendí que si estas variables no se configuran correctamente, los contenedores pueden fallar o no iniciar.
- Logré que WordPress se conecte a la base de datos MySQL dentro de la misma red.
- Observé que aunque se elimine un contenedor, la información no se pierde si se mantiene el servicio de base de datos.

### Consulta
**¿Cómo se gestionan datos confidenciales con los secretos de Docker (Docker Secrets)?**

Los Docker Secrets son una forma segura de manejar información sensible como contraseñas, tokens, certificados, claves API, dentro de contenedores sin exponerlos en variables de entorno o en el código.
- No se almacenan en la imagen
- No aparecen en docker inspect
- Están cifrados en el sistema (cuando usas Swarm)

Docker Secrets funciona con Docker Swarm en el cual se deben seguir ciertos pasos con:

- **Inicializar**
  
docker swarm init

- **Crear un secreto**
  
echo "mi_password_super_segura" | docker secret create db_password

- **Ver secretos**

docker secret ls

Docker no pasa secretos como variables de entorno, sino como archivos temporales en memoria.

### Conclusión
En conclusión, en esta práctica comprendí cómo configurar contenedores con variables de entorno, conectar servicios mediante redes, gestionar datos. Estos conocimientos son fundamentales para mi formación profesional, ya que me preparan para trabajar con arquitecturas modernas basadas en contenedores y despliegues más seguros y eficientes.


