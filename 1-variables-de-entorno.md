# Variables de Entorno
### ¿Qué son las variables de entorno?
Las variables de entorno son como ajustes a nivel del sistema operativo que ayudan a que los programas funcionen correctamente y sepan dónde encontrar recursos o cómo comportarse.

# COMPLETAR

### Para crear un contenedor con variables de entorno

```
docker run -d --name <nombre contenedor> -e <nombre variable1>=<valor1> -e <nombre variable2>=<valor2>
```

### Crear un contenedor a partir de la imagen de nginx:alpine con las siguientes variables de entorno: username y role. Para la variable de entorno rol asignar el valor admin.

<img width="854" height="65" alt="{0142C2AF-E691-4A67-9BA3-280B6686F752}" src="https://github.com/user-attachments/assets/5697f7ca-ee7f-45d6-ab03-dd2aea815cb5" />

# COMPLETAR

# CAPTURA CON LA COMPROBACIÓN DE LA CREACIÓN DE LAS VARIABLES DE ENTORNO DEL CONTENEDOR ANTERIOR

<img width="1579" height="617" alt="{A48B5CF5-F1C9-45E6-ACAD-6AE78B7439E9}" src="https://github.com/user-attachments/assets/634f601b-ca38-42de-82ad-16a97af9b702" />

### Crear un contenedor con la imagen de mysql, mapear todos los puertos
# COMPLETAR

<img width="1099" height="598" alt="{3C2930E0-56C3-435D-A5A0-564D78265EFE}" src="https://github.com/user-attachments/assets/677335b7-0a53-4b3d-bd5f-52bc233e1d85" />


### ¿El contenedor se está ejecutando?
No porque necesita de una variable de entorno asignada a la contraseña de estos tipos:
    - MYSQL_ROOT_PASSWORD
    - MYSQL_ALLOW_EMPTY_PASSWORD
    - MYSQL_RANDOM_ROOT_PASSWORD
    
# COMPLETAR

### Identificar el problema
# COMPLETAR

<img width="879" height="78" alt="{C4B53E8E-A7B9-4167-94EC-DB25954B6C7E}" src="https://github.com/user-attachments/assets/e3681738-f3f3-49d5-8c14-8152f1ba3d3b" />

### Para crear un contenedor con variables de entorno especificadas
- Portabilidad: Las aplicaciones se vuelven más portátiles y pueden ser desplegadas en diferentes entornos (desarrollo, pruebas, producción) simplemente cambiando el archivo de variables de entorno.
- Centralización: Todas las configuraciones importantes se centralizan en un solo lugar, lo que facilita la gestión y auditoría de las configuraciones.
- Consistencia: Asegura que todos los miembros del equipo de desarrollo o los entornos de despliegue utilicen las mismas configuraciones.
- Evitar Exposición en el Código: Mantener variables sensibles como contraseñas, claves API, y tokens fuera del código fuente reduce el riesgo de exposición accidental a través del control de versiones.
- Control de Acceso: Los archivos de variables de entorno pueden ser gestionados con permisos específicos, limitando quién puede ver o modificar la configuración sensible.

<img width="881" height="73" alt="{3BFDF2D7-1F07-49FE-9CEA-A2AC11FAA69A}" src="https://github.com/user-attachments/assets/8fad72f4-89a2-480b-8ae0-a7153b461479" />


### ¿Qué bases de datos existen en el contenedor creado?

<img width="967" height="590" alt="{615001E2-1F2A-454E-9FE8-E84CBDC292E6}" src="https://github.com/user-attachments/assets/e52a808c-575f-4319-8111-652b135514db" />

# COMPLETAR
