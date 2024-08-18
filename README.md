# Sistema de estacionamiento inteligente

## Autor : Diaz Mateo - mateo99.d@gmail.com

## Profesores : 
- Ariel Lutenberg 
- Sergio Caprile  
- Juan Manuel Reta 
- Eduardo Filomena

## 1. Selección de proyecto a implementar
Para seleccionar el proyecto final de este curso, fue necesario definir un grupo de proyectos posibles y evaluarlos basándonos en criterios técnicos y subjetivos. Para ello, se realizó una tabla comparativa en la que se asignó un peso a cada uno de los siguientes parámetros: tiempo y facilidad de implementación (alto), disponibilidad y costo del hardware (medio), motivación personal (medio), y utilidad del proyecto (medio).

En todos los casos, se asignó un puntaje del 1 al 10, donde 10 es lo más favorable y 1 lo menos favorable. Los pesos asignados consideraron dos aspectos principales: en primer lugar, con un peso mayor, se evaluó qué tan conveniente sería el proyecto una vez finalizado y qué tan factible sería llevarlo a cabo dentro del marco del proyecto final del curso.

El primer aspecto se centra en determinar si el proyecto tendría una vida útil, ya sea en un contexto académico o comercial. Por otro lado, el segundo aspecto evalúa la viabilidad del proyecto, considerando el presupuesto disponible y el entusiasmo generado en las personas involucradas.

A continuación, se describen las categorías con las cuales se evaluarán los proyectos:

- **_Tiempo de implementación_**: Este aspecto mide la viabilidad del proyecto dentro de un tiempo determinado, asegurando que pueda ser completado antes de la fecha límite. Se le otorgó una alta importancia debido a las restricciones temporales del curso.

- **_Disponibilidad y costo de hardware_**: Dado que el proyecto debe ser ensamblado físicamente, la disponibilidad del hardware es un aspecto fundamental. Además, el costo del hardware fue considerado, ya que un presupuesto limitado podría afectar la viabilidad del proyecto.

- **_Motivación personal_**: Aquí se asignó un puntaje en función del entusiasmo personal hacia cada propuesta. La predisposición y motivación de quienes realizan el proyecto son factores clave para su éxito.

- **_Utilidad del proyecto_**: Esta categoría evalúa si el proyecto ofrece una solución novedosa y relevante a un problema existente en el mercado.

## 1.2 Propuestas analizadas

Como trabajo final se analizaron las siguientes propuestas: 

* **Sintetizador y procesamiento de audio** : El sistema se basa en sintesis y procesamiento de señales para generar audio.  Aunque genera un alto entusiasmo personal, es un proyecto ambicioso para el tiempo disponible. La principal dificultad radica en procesar el sonido en tiempo real, lo cual requiere algoritmos eficientes y una gestión óptima de los recursos del microcontrolador.
    
* **GPS tracker**: Este proyecto consiste en la implementación de un GPS para su uso en diversos dispositivos. La dificultad radica en la disponibilidad del hardware y el conocimiento necesario sobre Radio Frecuencia para su implementación.

* **Sistema de estacionamiento inteligente**:  Este proyecto se centra en el control automatizado de un estacionamiento de vehículos. La idea es gestionar los espacios, permitir reservas, e interactuar con el usuario. Dado que es un prototipo, se pueden implementar estas funcionalidades con hardware relativamente económico, incluyendo módulos como SPI, Wi-Fi y LCD.

| Proyecto  |   | **_Tiempo de implementación (peso:10)_** | **_Disponibilidad y costo de hardware_(peso:8)** | **_Motivación personal_(peso=9)**: | **_Utilidad del proyecto_(peso=6)**: | **_Total puntuación ponderada_** |
|:------------: |:---------------:| :-------------:|:-----:|:-----:|:-----:|:-----:|
| **Sintetizador y procesamiento de audio**        | Puntuación          | 4        | 7  |9  |6  | - |
|       | Puntuación ponderada          | 40        |56  |81  |36  |213  |
| **GPS tracker**         | Puntuación         | 6        |4  |8  |7  |-  |
|         | Puntuación ponderada          | 60        |32  |72  |42  |206  |
| **Sistema de estacionamiento inteligente**        | Puntuación           | 7        |8  |8  |7  |-  |
|        | Puntuación ponderada         | 70       |64  |72  |42  |248  |


El proyecto de sintetizador y procesamiento de audio, aunque interesante, requiere optimizaciones significativas en el hardware y demandaría más tiempo del disponible. Estas razones llevaron a descartarlo. El GPS Tracker también es una buena opción, pero se necesitaba más tiempo para estudiar el módulo y el costo del hardware era elevado. Finalmente, se optó por el sistema de estacionamiento inteligente debido a su viabilidad y relevancia en el contexto del curso. Al ser un prototipo, el hardware puede limitarse a las funcionalidades más convenientes.

## Sistema de estacionamiento inteligente

Este proyecto tiene como objetivo desarrollar un sistema de estacionamiento inteligente que permita el control y monitoreo del servicio. Los usuarios podrán realizar reservas de espacios a través de internet utilizando una aplicación o interfaz web, mientras que aquellos sin reserva podrán verificar la disponibilidad en tiempo real mediante un display LCD en el lugar. La comunicación con los usuarios se llevará a cabo mediante Wi-Fi, y el propietario del estacionamiento podrá monitorear y controlar el sistema mediante una conexión UART a una PC.

Un motor servo simulará una barrera de acceso, la cual se abrirá o cerrará según la validación de la reserva o la disponibilidad de espacios.

En la Figura 1.1 se presenta un diagrama en bloques del proyecto, que abarca cuatro grandes grupos de periféricos: interfaz de usuario, sensores, control de tiempo real y actuadores.

![diagrama_de_bloques](https://github.com/mateooD/TP_Final_ArmBookCourse2024/blob/1-requirement-project/Figures/diagrama_bloques.png)

_Figura 1.1: Diagrama de bloques_

### Comparativa productos del mercado

El proyecto aborda un problema muy específico, por lo que no existe un producto de este tipo disponible en el mercado de manera inmediata. Además, cabe destacar que este proyecto es un prototipo con un enfoque más académico que comercial.

| Característica         | Park Assist                           | Cleverciti                              |
|------------------------|-------------------------------------------|-------------------------------------------|
| Reservas en Línea      | Sí                                        | Si                                        |
| Verificación de Disponibilidad en el Lugar         | Sí                                        | Si                                        |
| Guía Visual | Sí                                        | Si                                        |
| Control de Acceso               | Códigos QR o sistemas de identificación por matrícula          | Códigos QR o sistemas de identificación por matrícula   |
| Precio           | $10,000 y $50,000 USD                               | $20,000 a $60,000 USD                                 |

_Tabla 2: Comparación entre dos productos disponibles en el mercado_

### Requerimientos 
La Tabla 3 presenta los requerimientos del proyecto.


| Grupo de Requerimiento         | ID de Requerimiento                       | Descripción                                                                                                                                                                                                   |
|--------------------------------|-------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Monitoreo                        | 1.1                                       | El sistema debe mostrar la disponibilidad de espacios en tiempo real como asi tambien en la app.                                                                                                            |
| Monitoreo                        | 1.2                                       | El sistema debe proporcionar información sobre el estado general del sistema al propietario, permitiéndole realizar diagnósticos básicos desde la pantalla LCD o la aplicación.                             |
| Conectividad                         | 2.1                                       |El sistema debe permitir a los usuarios realizar reservas de espacios de estacionamiento a través de una aplicación o página web mediante Wi-Fi.                                                         |
| Conectividad                   | 2.2                                       | El sistema debe permitir al propietario realizar un monitoreo detallado y control remoto del sistema a través de una conexión UART a una PC, incluyendo opciones avanzadas de configuración y diagnóstico .   |
| Mecánica                   | 3.1                                       | El sistema debe controlar un motor servo que simula una barrera, la cual se abrirá o cerrará en función de la validación de la reserva o la disponibilidad de espacios.                                           |
| Configuración                       | 4.1                                       |  El sistema debe proporcionar a los usuarios un código único para cada reserva, que se utilizará para acceder al estacionamiento.                                                                        |
| Configuración                       | 4.2                                       |  El sistema debe ser escalable para permitir la integración de más funcionalidades en el futuro, como la gestión de pagos o la expansión a más espacios de estacionamiento.                              |
| Configuración                   | 4.3                                       | La interfaz de usuario debe ser fácil de usar e intuitiva, tanto en la aplicación/web como en la pantalla LCD del estacionamiento.                                                                           |
| Tiempo de Ejecución                   | 5.1                                       | El proyecto se entregará antes del 17 de Septiembre de 2024.                                                                                                                                           |
| Manual de uso y Documentación                   | 6.1                                       | El código del sistema embebido estará disponible en un repositorio git, acompañado de un informe detallado con lista de partes, diagramas de conexión, requerimientos cumplidos, forma de uso y conclusiones.|
| Costo                  | 7.1                                       | El costo del dispositivo será menor a los 50 dólares.                                                                               

_Tabla 3: Requerimientos del sistema_


### Casos de uso

### Caso 1 - Reservar un Espacio de Estacionamiento

| Elemento de Caso de Uso | Definición                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|-------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Disparador              |El usuario desea reservar un espacio de estacionamiento antes de llegar al lugar.                                                                                                                                                                                                                                                                                                                                                           |
| Precondición            | El usuario tiene acceso a la aplicación o página web del sistema y está autenticado.                                                                                                                                                                                                                                                                                                                                                            |
| Flujo Básico            | El usuario abre la aplicación del servidor. El sistema muestra la disponibilidad de lugares. El usuario reserva el lugar y el sistema le brinda un codigo.                                                                                                                                                                                                                                                                                                   |
| Flujo Alternativo | Si el usuario intenta reservar un espacio que ya está ocupado, el sistema muestra un mensaje de error y permite seleccionar otro espacio. |

_Tabla 4: Caso de uso número 1_

### Caso 2 - Verificar Disponibilidad de Espacios en el Estacionamiento

| Elemento de Caso de Uso | Definición                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|-------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Disparador              |El usuario desea verificar la disponibilidad de espacios en el estacionamiento al llegar al lugar.                                                                                                                                                                                                                                                                                                                                                           |
| Precondición            | 	El usuario está físicamente en el estacionamiento y puede ver el display LCD.                                                                                                                                                                                                                                                                                                                                                            |
| Flujo Básico            |El usuario consulta la disponibilidad en el display LCD ubicado en el estacionamiento. El sistema muestra el número de espacios disponibles en tiempo real.El usuario selecciona un boton definido en el teclado e ingresa al lugar.                                                                                                                                                                                                                                                                                                   |
| Flujo Alternativo | Si no hay espacios disponibles, el sistema muestra un mensaje indicando que el estacionamiento está lleno. |

_Tabla 5: Caso de uso número 2_

### Caso 3 - Control y Monitoreo del Sistema desde la PC

| Elemento de Caso de Uso | Definición                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|-------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Disparador              |El propietario o administrador del estacionamiento desea monitorear o controlar el sistema desde una PC.                                                                                                                                                                                                                                                                                                                                                           |
| Precondición            | El sistema está conectado a una PC mediante UART, y el propietario tiene acceso autorizado a la PC.                                                                                                                                                                                                                                                                                                                                                            |
| Flujo Básico            |El propietario accede a la interfaz de control en la PC. El sistema muestra el estado actual del estacionamiento, incluyendo la disponibilidad de espacios y el estado de la barrera. El propietario puede realizar acciones de control, como abrir o cerrar la barrera, o actualizar manualmente el estado de la disponibilidad.El sistema responde a las acciones del propietario en tiempo real.                                                                                                                                                                                                                                                                                                   |
| Flujo Alternativo | Si la conexión UART falla, el sistema muestra un mensaje de error en la PC y deshabilita las acciones de control remoto hasta que se restablezca la conexión. Si el propietario intenta realizar una acción no permitida o fuera de su autorización, el sistema rechaza la operación y muestra un mensaje de advertencia. |

_Tabla 6: Caso de uso número 3_

