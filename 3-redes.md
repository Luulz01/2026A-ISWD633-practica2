# Redes

Las redes son un componente fundamental que permite la comunicación entre contenedores, así como la comunicación de los contenedores con el mundo exterior.


![Imagen](redes.PNG)

* Bridge: Esta es la red por defecto en Docker. Permite la comunicación entre contenedores en el mismo host. Cada contenedor conectado a la red bridge tiene una IP propia en la subred de la red bridge.

  * Brige por default: Cuando se ejecuta un contenedor, Docker crea automáticamente una red de tipo bridge por default. Esta red se utiliza para permitir la comunicación entre contenedores en el mismo host. Cada contenedor conectado a esta red obtiene su propia dirección IP en la subred de la red bridge.
  * Bridge creada por nosotros: Un usuario también puede crear sus propias redes de tipo bridge en Docker. Esto puede ser útil para organizar y segmentar los contenedores de una aplicación de manera más controlada. Al crear una red bridge personalizada, se puede especificar un rango de direcciones IP y otras configuraciones de red específicas. Los contenedores conectados a esta red utilizarán las direcciones IP de la subred definida por el usuario.
* Host: Con esta red, los contenedores comparten la red del host en lugar de tener su propia interfaz de red. Esto puede mejorar el rendimiento de red, pero los contenedores pueden entrar en conflicto con los puertos del host si intentan utilizar los mismos puertos.
* None: Con esta red, se deshabilita la configuración de red. Los contenedores que usan esta red tienen su propia red de loopback y no pueden comunicarse con otros contenedores a menos que se conecten explícitamente a una red.

### Crear una red de tipo bridge

```
docker network create <nombre red> -d bridge
```

### Crear un contenedor vinculado a una red

```
docker run -d --name <nombre contenedor> --network <nombre red> <nombre imagen>
```

### Para saber a qué red está conectado un contenedor

```
docker inspect <nombre contenedor>
```

ó

```
docker network inspect <nombre red> 
```

### Vincular contenedor a una red

```
docker network connect <nombre red> <nombre contenedor>
```

### Para desvincular un contenedor de una red

```
docker network disconnect <nombre red> <nombre contenedor>
```

### Para listar las redes existentes

```
docker network ls
```

### Crear los contenedores y las redes que se presentan en el esquema. Usar para todos los contenedores la imagen de nginx:alpine

![Imagen](esquema-ejercicio-redes.PNG)

# COLOCAR UNA CAPTURA DE LAS REDES EXISTENTES CREADAS

Creación de las redes

<img width="666" height="125" alt="{8457A954-6022-4A1E-AD3B-D09B001911C7}" src="https://github.com/user-attachments/assets/8e3fdc4a-d584-47df-a155-d65dee696c34" />

Redes existentes

<img width="483" height="194" alt="{86C891B9-7BD0-4CA6-9851-368F3BCF3D86}" src="https://github.com/user-attachments/assets/1ceb28ac-12bc-47c5-8b51-05860b112bc0" />



# COLOCAR UNA(S) CAPTURAS(S) DE LOS CONTENEDORES CREADOS EN DONDE SE EVIDENCIE A QUÉ RED ESTÁN VINCULADOS

<img width="845" height="285" alt="{F3B20B18-34E1-4F1B-98E3-4D8F1E918BF7}" src="https://github.com/user-attachments/assets/ae9f9458-d88d-41bc-92e3-31a0f057ad64" />

Red net-curso01 contenedores vinculados

<img width="1093" height="999" alt="{E18F35A6-C0A0-4071-828B-C74F6B867D31}" src="https://github.com/user-attachments/assets/52bc52f1-7a0a-4c38-8082-9963ffb852e5" />

<img width="1129" height="996" alt="{00301538-81C9-4CA9-9453-54B5DC344B75}" src="https://github.com/user-attachments/assets/9ddf904e-74cf-4db9-9edf-054cff30de3f" />

Red net-curso02 contenedores vinculados

<img width="942" height="982" alt="{F087CE27-839E-49B3-9E1C-44D86204E688}" src="https://github.com/user-attachments/assets/5dc975c6-bb21-425c-bfe3-53454cc5669e" />


### Para eliminar las redes creadas

```
docker network rm <nombre de la red>
```

