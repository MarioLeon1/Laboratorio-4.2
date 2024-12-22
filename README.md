# Configuración de Jenkins y Despliegue de Aplicación Web

Este documento describe el proceso paso a paso para configurar un entorno Jenkins distribuido y realizar un despliegue exitoso de una aplicación web.

## 1. Acceso Inicial a Jenkins

Para comenzar, necesitamos acceder a Jenkins por primera vez. Al iniciar Jenkins, se nos presenta una pantalla de login que requiere una contraseña inicial de administrador.

![Log in Jenkins](https://github.com/user-attachments/assets/835b6c7b-6692-4276-925f-d69458e4fbac)

Para obtener esta contraseña, ejecutamos el siguiente comando en la terminal:

```bash
docker-compose exec jenkins-master cat /var/jenkins_home/secrets/initialAdminPassword
```

![Conseguir contraseña](https://github.com/user-attachments/assets/a030d503-4b6c-4c56-a12e-c64b83dfbfe8)


Una vez introducida la contraseña correctamente, accedemos a Jenkins:

![Acceso a Jenkins](https://github.com/user-attachments/assets/56cf24ec-308f-4bb2-89ec-24c78cd8d48c)


## 2. Configuración Inicial

Después del primer acceso, Jenkins nos presenta una pantalla de bienvenida donde podemos comenzar la configuración inicial:

![Bienvenida a Jenkins](https://github.com/user-attachments/assets/c1954917-5560-4e3e-99b0-cc06884e862e)


## 3. Configuración de Nodos y Agentes

Para establecer un entorno distribuido, necesitamos configurar los nodos y agentes de Jenkins. Accedemos a la sección de nodos:

![Pantalla de nodes](https://github.com/user-attachments/assets/15acd7c4-073f-4537-8b1d-d6160b3fed62)


### 3.1 Creación de un Nuevo Nodo

Procedemos a crear un nuevo nodo que actuará como agente:

![Creando nuevo node](https://github.com/user-attachments/assets/eb910cf8-2908-4b57-b565-5b65416462b6)


### 3.2 Configuración del Agente

Configuramos los detalles específicos del agente Jenkins:

![Creando nuevo agente](https://github.com/user-attachments/assets/223602a1-6cb9-4d40-9bb1-68c1ba1630f0)


### 3.3 Configuración de Credenciales

Para la comunicación segura entre el master y el agente, necesitamos configurar las credenciales SSH:

![Credenciales agente Jenkins](https://github.com/user-attachments/assets/37fccbbe-5dc7-4607-af86-723d76341951)


### 3.4 Generación de Claves RSA

Generamos un nuevo par de claves RSA para la autenticación:

![Generando claves RSA](https://github.com/user-attachments/assets/35b126f2-b701-4a3f-8fbe-423be3789ae9)


Verificamos la creación exitosa de las claves:

![Clave RSA creada](https://github.com/user-attachments/assets/47c99e74-6348-4642-b7b3-882390e686ec)


## 4. Configuración del Pipeline

### 4.1 Creación del Pipeline

Creamos un nuevo pipeline para automatizar el proceso de despliegue:

![Nuevo Pipeline](https://github.com/user-attachments/assets/be65646a-288c-4d85-956d-9f5df79dc6c9)


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
