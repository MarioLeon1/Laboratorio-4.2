# Configuración de Jenkins y Despliegue de Aplicación Web

Este documento describe el proceso paso a paso para configurar un entorno Jenkins distribuido y realizar un despliegue exitoso de una aplicación web.

## 1. Acceso Inicial a Jenkins

Para comenzar, necesitamos acceder a Jenkins por primera vez. Al iniciar Jenkins, se nos presenta una pantalla de login que requiere una contraseña inicial de administrador.

![Log in Jenkins](imagenes\image.png)

Para obtener esta contraseña, ejecutamos el siguiente comando en la terminal:

```bash
docker-compose exec jenkins-master cat /var/jenkins_home/secrets/initialAdminPassword
```

![Conseguir contraseña](imagenes\image-1.png)

Una vez introducida la contraseña correctamente, accedemos a Jenkins:

![Accedido a Jenkins](imagenes\image-2.png)

## 2. Configuración Inicial

Después del primer acceso, Jenkins nos presenta una pantalla de bienvenida donde podemos comenzar la configuración inicial:

![Bienvenida a Jenkins](imagenes\image-3.png)

## 3. Configuración de Nodos y Agentes

Para establecer un entorno distribuido, necesitamos configurar los nodos y agentes de Jenkins. Accedemos a la sección de nodos:

![Pantalla de nodes](imagenes\image-4.png)

### 3.1 Creación de un Nuevo Nodo

Procedemos a crear un nuevo nodo que actuará como agente:

![Creando nuevo node](imagenes\image-5.png)

### 3.2 Configuración del Agente

Configuramos los detalles específicos del agente Jenkins:

![Creando nuevo agente](imagenes\image-9.png)

### 3.3 Configuración de Credenciales

Para la comunicación segura entre el master y el agente, necesitamos configurar las credenciales SSH:

![Credenciales agente Jenkins](imagenes\image-6.png)

### 3.4 Generación de Claves RSA

Generamos un nuevo par de claves RSA para la autenticación:

![Generando credenciales públicas RSA](imagenes\image-7.png)

Verificamos la creación exitosa de las claves:

![Clave RSA creada](imagenes\image-8.png)

## 4. Configuración del Pipeline

### 4.1 Creación del Pipeline

Creamos un nuevo pipeline para automatizar el proceso de despliegue:

![Nuevo Pipeline](imagenes\image-10.png)

### 4.2 Configuración del Pipeline

Configuramos los detalles del pipeline, incluyendo la conexión con el repositorio de código:

![Configuración Pipeline](imagenes\image-11.png)

## 5. Ejecución y Verificación

### 5.1 Ejecución del Pipeline

Iniciamos la ejecución del pipeline para comenzar el proceso de despliegue:

![Ejecutamos la pipeline](imagenes\image-12.png)

### 5.2 Verificación del Despliegue

Finalmente, verificamos que la aplicación web se ha desplegado correctamente:

![Web desplegada correctamente](imagenes\image-13.png)

## Conclusión

Con estos pasos, hemos logrado configurar exitosamente un entorno Jenkins distribuido y realizar un despliegue automatizado de nuestra aplicación web.