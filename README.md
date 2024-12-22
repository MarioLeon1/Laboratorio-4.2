# Configuración de Jenkins y despliegue de aplicación web

Este documento describe el proceso paso a paso para configurar el entorno Jenkins distribuido en el primer repositorio y realizar un despliegue exitoso de la aplicación web del segundo repositorio.

## 1. Acceso Inicial a Jenkins

Para comenzar, necesitamos acceder a Jenkins por primera vez. Al iniciar Jenkins, se nos presenta una pantalla de login que requiere una contraseña inicial de administrador.

![Log in Jenkins](https://github.com/user-attachments/assets/835b6c7b-6692-4276-925f-d69458e4fbac)

Para obtener esta contraseña, ejecutamos el siguiente comando en la terminal:

```bash
docker-compose exec jenkins-master cat /var/jenkins_home/secrets/initialAdminPassword
```

![Conseguir contraseña](https://github.com/user-attachments/assets/a030d503-4b6c-4c56-a12e-c64b83dfbfe8)


Una vez introducida la contraseña correctamente, accedemos a Jenkins:

![Acceso a Jenkins](https://github.com/user-attachments/assets/02c8d000-ceb5-4a8e-b71d-72e68482e76c)


## 2. Configuración Inicial

Después del primer acceso, Jenkins nos presenta una pantalla de bienvenida donde podemos comenzar la configuración inicial:

![Bienvenida a Jenkins](https://github.com/user-attachments/assets/c1954917-5560-4e3e-99b0-cc06884e862e)


## 3. Configuración de Nodos y Agentes

Para establecer un entorno distribuido, necesitamos configurar los nodos y agentes de Jenkins. Accedemos a la sección de nodos:

![Pantalla de nodes](https://github.com/user-attachments/assets/d5903d94-eda3-4945-a662-b4312304021f)


### 3.1 Creación de un Nuevo Nodo

Procedemos a crear un nuevo nodo que actuará como agente:

![Creando nuevo node](https://github.com/user-attachments/assets/eb910cf8-2908-4b57-b565-5b65416462b6)


### 3.2 Configuración del Agente

Configuramos los detalles específicos del agente Jenkins:

![Nuevo agente](https://github.com/user-attachments/assets/3b3a72f9-714d-4bce-b467-18fe6554a6b0)



### 3.3 Configuración de Credenciales

Para la comunicación segura entre el master y el agente, necesitamos configurar las credenciales SSH:

![Credenciales Jenkins](https://github.com/user-attachments/assets/ba19ced3-b366-4ab7-a907-9b4ecacfc252)


### 3.4 Generación de Claves RSA

Generamos un nuevo par de claves RSA para la autenticación:

![RSA](https://github.com/user-attachments/assets/7e9aa792-528d-4e20-b4d5-cb127324b135)




Verificamos la creación exitosa de las claves:

![RSA creado](https://github.com/user-attachments/assets/f918aeac-9910-4924-985e-d3b60b14bf01)



## 4. Configuración del Pipeline

### 4.1 Creación del Pipeline

Creamos un nuevo pipeline para automatizar el proceso de despliegue:

![Nuevo pipeline](https://github.com/user-attachments/assets/036e102f-3efc-4316-9573-2d34bbe26a43)



### 4.2 Configuración del Pipeline

Configuramos los detalles del pipeline, incluyendo la conexión con el repositorio de código:

![Configurando Pipeline](https://github.com/user-attachments/assets/3a655d76-4670-4457-ac5f-d3599aed1e67)


## 5. Ejecución y Verificación

### 5.1 Ejecución del Pipeline

Iniciamos la ejecución del pipeline para comenzar el proceso de despliegue:

![Ejecutando Pipeline](https://github.com/user-attachments/assets/ed394467-8f9e-4af7-950b-d1301c3d011f)

### 5.2 Verificación del Despliegue

Finalmente, verificamos que la aplicación web se ha desplegado correctamente:

![Web desplegada correctamente](https://github.com/user-attachments/assets/29e0e297-eec0-4e0d-aa37-bd9e919b5c7d)


## Conclusión

Con estos pasos, hemos logrado configurar exitosamente un entorno Jenkins distribuido y realizar un despliegue automatizado de nuestra aplicación web.
