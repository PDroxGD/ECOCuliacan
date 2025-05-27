# ECO Culiacán: Sistema Inteligente de Gestión de Residuos

<img src="/public/images/ECO.png" alt="Logo de ECO Culiacán" width="200"/>


** Producto 2: Código y Documentación**

##  Integrantes del Equipo

* Chávez Armenta Tania Elena.
* Madero Meza Pedro Faustino.
* Urías Jacobo Lesley Kirey.
* Juarez Verdugo Michelle Alejandra..


Culiacán, Sinaloa, México. Mayo de 2025.

##  Tabla de Contenidos

-   [Introducción](#-introducción)
-   [Resumen del Sistema](#-resumen-del-sistema)
-   [Requisitos](#-requisitos)
    -   [Funcionales y No Funcionales](#funcionales-y-no-funcionales)
    -   [Técnicos](#técnicos)
-   [Arquitectura del Sistema](#-arquitectura-del-sistema)
-   [Tecnologías Utilizadas](#-tecnologías-utilizadas)
-   [Estructura del Proyecto](#-estructura-del-proyecto)
-   [Instalación](#-instalación)
    -   [Prerrequisitos](#prerrequisitos)
    -   [Configuración del Entorno](#configuración-del-entorno)
    -   [Ejecución del Proyecto](#ejecución-del-proyecto)
-   [Uso del Sistema](#-uso-del-sistema)
    -   [Clase CRUD Implementada](#clase-crud-implementada)
    -   [Flujo de Uso](#flujo-de-uso)
-   [Rutas de la Aplicación Web](#-rutas-de-la-aplicación-web)
-   [Base de Datos (Modelado)](#-base-de-datos-modelado)
-   [Mantenimiento y Actualizaciones](#-mantenimiento-y-actualizaciones)
-   [Pruebas](#-pruebas)
-   [Seguridad](#-seguridad)
-   [Referencias y Recursos](#-referencias-y-recursos)
-   [Contacto](#-contacto)

---

## Introducción

La gestión tradicional de residuos en Culiacán a menudo presenta desafíos en cuanto a eficiencia, planificación y comodidad para la ciudadanía, generando inconvenientes y afectando el entorno urbano. Ante esta necesidad de optimización y con la visión de construir una ciudad más limpia y sostenible, presentamos ECO Culiacán, un sistema innovador diseñado para revolucionar la forma en que los usuarios solicitan y programan la recolección de su basura, ofreciendo un servicio más eficiente a las necesidades de la población.

Este documento y el código adjunto corresponden al **Producto 2** del curso, centrándonos en el desarrollo del portal web, la autenticación de usuarios y la implementación de una funcionalidad CRUD esencial.

## Resumen del Sistema

ECO Culiacán es un sistema inteligente de gestión de residuos cuyo objetivo es optimizar la recolección de basura, facilitar la interacción entre ciudadanos y personal de recolección, y promover una ciudad más limpia y sostenible en Culiacán, Sinaloa. A través de un portal web intuitivo, los usuarios pueden registrarse, iniciar sesión y gestionar sus interacciones con el sistema de recolección.

## Requisitos

### Funcionales y No Funcionales

**Requisitos Funcionales:**

* **RF1: Autenticación de Usuarios:**
    * RF1.1: El sistema debe permitir a los usuarios registrarse con un nombre de usuario y contraseña.
    * RF1.2: El sistema debe permitir a los usuarios iniciar sesión con sus credenciales registradas.
    * RF1.3: El sistema debe mantener la sesión del usuario activa mientras navega por las páginas protegidas.
    * RF1.4: El sistema debe permitir a los usuarios cerrar sesión de forma segura.
* **RF2: Gestión de [Nombre de tu Clase CRUD, ej. Reportes]:**
    * RF2.1: El sistema debe permitir a los usuarios [Crear/Registrar] nuevos [ej. reportes de basura].

* **RF3: Interfaz de Usuario:**
    * RF3.1: La interfaz del portal web debe ser intuitiva y fácil de usar.
    * RF3.2: El sistema debe mostrar mensajes claros de éxito o error al usuario (notificaciones flash).

**Requisitos No Funcionales:**

* **RNF1: Usabilidad:**
    * RNF1.1: La interfaz de usuario debe ser responsiva y adaptarse correctamente a diferentes tamaños de pantalla (escritorio, tabletas, móviles).
    * RNF1.2: El flujo de registro e inicio de sesión debe ser directo y sin pasos innecesarios.
* **RNF2: Rendimiento:**
    * RNF2.1: El tiempo de respuesta de las operaciones principales (login, registro, CRUD) no debe exceder los 3 segundos.
* **RNF3: Seguridad:**
    * RNF3.1: Las contraseñas de los usuarios deben ser almacenadas de forma segura (encriptadas).
    * RNF3.2: Las sesiones de usuario deben ser gestionadas de forma segura.
* **RNF4: Mantenibilidad:**
    * RNF4.1: El código debe estar organizado y comentado para facilitar su comprensión y futuras modificaciones.

### Técnicos

* **Entorno de Desarrollo:** Node.js.
* **Gestor de Paquetes:** npm.
* **Base de Datos:** MongoDB.
* **Navegador Web:** Compatible con los navegadores modernos (Chrome, Firefox, Edge, Safari).

## Arquitectura del Sistema

El sistema ECO Culiacán sigue una arquitectura **Cliente-Servidor en Capas**, diseñada para ser modular, escalable y fácil de mantener. Se compone principalmente de una aplicación móvil (futuro desarrollo), un portal web (este proyecto), un servidor backend y una base de datos.

**Componentes Principales:**

* **Cliente Móvil y Web:** Representan las interfaces de usuario a través de las cuales los ciudadanos interactúan con el sistema. El Portal Web (este proyecto) es uno de los clientes.
* **Servidor Backend:** El corazón de la aplicación, implementado con Node.js y Express.js, encargado de la lógica de negocio, procesamiento de solicitudes y comunicación con la base de datos.
* **Base de Datos (MongoDB):** Almacena de forma persistente toda la información del sistema, como datos de usuarios, reportes de residuos, rutas, etc.
* **API REST:** El canal de comunicación estandarizado que permite la interacción entre los clientes (móvil y web) y el servidor backend.

Esta arquitectura fue elegida por su **modularidad**, **facilidad de mantenimiento** y **escalabilidad**, permitiendo que los componentes funcionen de forma independiente y facilitando futuras mejoras y adaptaciones.

## Tecnologías Utilizadas

### Frontend (Portal Web)
* **HTML5:** Estructura de la página web.
* **CSS3:** Estilos y diseño responsivo.
* **EJS (Embedded JavaScript):** Motor de plantillas para renderizar vistas dinámicas desde el servidor.
* **JavaScript (Vanilla JS):** Lógica del lado del cliente para interactividad (ej. mostrar/ocultar contraseña).

### Backend (Parte del servidor para este proyecto)
* **Node.js:** Entorno de ejecución JavaScript del lado del servidor.
* **Express.js:** Framework web para Node.js, utilizado para construir la API y gestionar rutas.
* **`express-session`:** Middleware para manejar sesiones de usuario.
* **`connect-flash`:** Middleware para mensajes flash (notificaciones temporales).
* **`passport` & `passport-local`:** Módulos para autenticación de usuarios (estrategia local con usuario y contraseña).
* **`bcryptjs`:** Librería para cifrado de contraseñas (hashing).
* **Mongoose:** Librería para modelado de objetos MongoDB en Node.js, facilitando la interacción con la base de datos.

### Base de Datos
* **MongoDB:** Base de datos NoSQL orientada a documentos.



## Estructura del Proyecto
    ├── public/                # Archivos estáticos (CSS, JS del cliente, imágenes)
    │   ├── css/
    │   │   └── style.css      # Estilos globales
    │   ├── images/
    │   │   ├── ECO.png
    │   │   ├── facebook.png
    │   │   ├── twitter.png
    │   │   ├── ig.png
    │   │   ├── usuario.png
    │   │   ├── iconousuario.png
    │   │   ├── ojo.png
    │   │   └── ojoff.png
    ├── views/                 # Archivos de plantillas EJS
    │   ├── login.ejs          # Página de inicio de sesión
    │   ├── registro.ejs       # Página de registro
    │   ├── lBienvenida.ejs    # Página de bienvenida
    │   └── index.ejs          # Página de inicio
    ├── config/                # Configuraciones (ej. base de datos, Passport)
    │   ├── passport.js        # Configuración de Passport
    │   └── db.js              # Configuración de conexión a la base de datos (MongoDB)
    ├── models/                # Definición de esquemas y modelos de Mongoose
    │   ├── User.js            # Esquema y modelo para usuarios
    │   └── Report.js          # Esquema y modelo para reportes
    ├── server.js              # Archivo principal de la aplicación Node.js
    ├── package.json           # Metadatos del proyecto y dependencias
    ├── package-lock.json      # Bloqueo de versiones de dependencias
    └── README.md              # Este archivo
## Instalación y Uso 

Sigue estos pasos para configurar y ejecutar el proyecto en tu máquina local.

### Prerrequisitos

Asegúrate de tener instalado lo siguiente:

* **Node.js** (versión 14 o superior recomendada)
* **npm** (viene con Node.js)
* **MongoDB Server** 

### Configuración del Entorno

1.  **Clona este repositorio:**
    ```bash
    git clone https://github.com/TaniaElenaa/ECOCuliacan
    cd ECOCuliacan
    ```

2.  **Instala las dependencias de Node.js:**
    ```bash
    npm install
    ```

3.  **Configura tu base de datos MongoDB:**
    * Asegúrate de que tu servidor MongoDB esté corriendo.
    * En tu archivo de configuración de la base de datos (por ejemplo, `config/db.js`), especifica la URL de conexión a tu instancia de MongoDB. Por ejemplo: `mongodb://localhost:27017/eco_culiacan_db`.
    * **Importante:** Deberás definir un modelo de usuario (por ejemplo, en `models/User.js`) usando Mongoose, con campos para `username` y `password` que Passport.js usará para la autenticación.

### Ejecución del Proyecto

1.  **Inicia el servidor MongoDB.**
2.  **Ejecuta la aplicación Node.js:**
    ```bash
    npm start
    ```
    o si no tienes `npm start` configurado en `package.json`:
    ```bash
    node server.js
    ```
  

3.  **Accede a la aplicación:**
    Abre tu navegador web y navega a `http://localhost:3000` 

## Rutas de la Aplicación Web

* `/`: Página de inicio (puede redirigir a `/login` si no hay sesión).
* `/login`: Página de inicio de sesión.
* `/register`: Página de registro de nuevos usuarios.
* `/logout`: Cierra la sesión del usuario.




## Contacto

Para cualquier pregunta o comentario, puedes contactar al equipo de ECO Culiacán:

* **Twitter/X:** [x.com/ECOCuliacan](https://x.com/ECOCuliacan)
* **Facebook:** [ECO Culiacán en Facebook](https://www.facebook.com/people/ECO-Culiac%C3%A1n/61576558111783/)
* **Instagram:** [eco.culiacan en Instagram](https://www.instagram.com/eco.culiacan/profilecard/)

---
