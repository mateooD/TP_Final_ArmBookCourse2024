# Sistema de estacionamiento inteligente

## Autor : Diaz Mateo - mateo99.d@gmail.com

## Profesores : 
- Ariel Lutenberg 
- Sergio Caprile  
- Juan Manuel Reta 
- Eduardo Filomena

## 1. Selección de proyecto a implementar
Para comenzar el proceso de selección del proyecto final de este curso fue necesario definir un grupo de proyectos posibles y evaluarlos basandonos en criterios tecnicos y subjetivos. Para ello se realizó una tabla comparativa en donde se le asignó un peso a cada uno de los siguientes parámetros: tiempo y facilidad de implementación (alto), la disponibilidad y costo de hardware (medio), motivación personal (media) y utilidad del proyecto (medio).

En todos los casos se asignará un puntaje del 1 al 10 en donde 10 es lo más favorable y 1, lo menos. Para asignar los pesos se consideraron dos aspectos: en primer lugar y con un peso mayor, que tan conveniente resultará el proyecto una vez realizado y que tan posible sería llevarlo a cabo en el marco del proyecto final del curso.
El primer aspecto se dedica a determinar si existe una vida útil del proyecto una vez culminado ya sea en un ámbito académico o posiblemente comercial.
Por otro lado, el segundo aspecto determina si es posible finalizar el proyecto considerando el presupuesto destinado al proyecto y el entusiasmo que genera en las personas destinadas a este fin.

A continuación, se describen las categorías con las cuales se evaluarán los proyectos:

- **_Tiempo de implementación_**: Este aspecto representa la factibilidad en un tiempo dado del proyecto, es lo que permite que el proyecto pueda ser terminado antes de la fecha de entrega. En éste caso se le dará bastante importancia dado el tiempo límite del proyecto. 

- **_Disponibilidad y costo de hardware_**: Teniendo en cuenta que el proyecto deberá ser ensamblado físicamente, la disponibilidad del hardware es extremadamente importante y tal vez el aspecto más fundamental.

- **_Motivación personal_**: Aquí se asignará un puntaje de manera objetiva según el entusiasmo que me produce la propuesta en cuestión. Considero que para llevar a cabo un proyecto la predisposición  de las personas a cargo de este es un factor relevante.

- **_Utilidad del proyecto_**: En esta categoría se evaluará si el proyecto propone una solución inexistente en el mercado a un problema relevante.


## 1.2 Propuestas analizadas
Como trabajo final se analizaron las siguientes propuestas: 

* **Sintetizador y procesamiento de audio** : El sistema se basa en sintesis y procesamiento de señales para generar audio. A nivel personal generaba bastante entusiasmo pero era un proyecto ambicioso para el tiempo que se tiene. Lo desafiante de estos proyectos es procesar el sonido a tiempo real, lo que lleva a procesar señales con alto procesamiento. Esto representa una limitación que dependerá de la eficiencia de los algoritmos utilizados y el buena gestión de los recursos del microcontrolador.
    
    
* **GPS tracker**: Este proyecto consiste en la utilización de un GPS para la utilización en diversos dispositivos. La dificultad en este proyecto radicaba en la disponibilidad del hardware como asi tambien el conocimiento que se debe tener sobre Radio Frecuencias para la implementación de el mismo.

* **Sistema de estacionamiento inteligente**: Se trata de un sistema de control de un estacionamiento de vehiculos automatizado. La idea se se basa en el control de lugares, reservas de los mismos e interaccion con el usuario. Teniendo en cuenta que es un prototipo podemos implementar dichas funcionalidades con hardware erlativamente economico, incorporando tambien diversos modulos (SPI,WIFI,LCD).

| Proyecto  |   | **_Tiempo de implementación (peso:10)_** | **_Disponibilidad y costo de hardware_(peso:8)** | **_Motivación personal_(peso=9)**: | **_Utilidad del proyecto_(peso=6)**: | **_Total puntuación ponderada_** |
|:------------: |:---------------:| :-------------:|:-----:|:-----:|:-----:|:-----:|
| **Sintetizador y procesamiento de audio**        | Puntuación          | 4        | 7  |9  |6  | - |
|       | Puntuación ponderada          | 40        |56  |81  |36  |213  |
| **GPS tracker**         | Puntuación         | 6        |4  |8  |7  |-  |
|         | Puntuación ponderada          | 60        |32  |72  |42  |206  |
| **Sistema de estacionamiento inteligente**        | Puntuación           | 7        |8  |8  |7  |-  |
|        | Puntuación ponderada         | 70       |64  |72  |42  |248  |


En efecto, el proyecto de sintetizador y procesamiento de audio necesitaba optimizar cuestiones del hardware y sobre todo habría necesitado demasiado tiempo. Son las razones por las cuales no le elegí. 
El GPS tracker podría ser una buena idea de proyecto también pero se necesitaba mas tiempo para el estudio de el modulo, como asi tambien los costos de el mismo.  
Finalmente , el sistema de estacionamiento inteligente es el proyecto que elegí para el final del curso de  Sistemas Embebidos. 
Se eligió dicho proyecto ya que al tratarse de un trabajo de final de curso podemos tomar la situacion como un prototipo, es por ello que el hardware lo podemos limitar a las funcionalidades que nos parezcan mas convenientes.

## Sistema de estacionamiento inteligente

El proyecto consiste en desarrollar un sistema de estacionamiento inteligente que permite el control y monitoreo del servicio. Los usuarios podrán realizar reservas de espacios de estacionamiento a través de internet utilizando una aplicación o interfaz web, y aquellos sin reserva podrán verificar la disponibilidad en tiempo real mediante un display LCD en el lugar. La comunicación entre el sistema y los usuarios se llevará a cabo mediante WiFi, mientras que el propietario del estacionamiento podrá monitorear y controlar el sistema mediante una conexión UART a una PC.

Un motor servo simulará una barrera de acceso que permitirá o denegará el ingreso de vehículos en función de la validación de la reserva o disponibilidad de espacios.

En la Fig. 1.1 se muestra un diagrama en bloques del proyecto. Se observan cuatro grandes grupos de periféricos: interfaz de usuario, sensores, control de tiempo real y actuadores. 

El primero consiste en un módulo WiFi que se utilizara para la comunicación con el Bot de Telegram, y un display LCD que mostrará la información pertinente en pantalla para una rápida visualización. El segundo consiste en dos sensores: un sensor de temperatura y un sensor de sólidos disueltos totales para monitorear el estado del agua. El tercero consiste en un módulo RTC para poder llevar un control preciso del tiempo para las funciones por tiempo. El último consiste en el motor paso a paso que será el responsable de girar el recipiente de alimento de forma que caiga una dosis en cada iteración.

(imagen)

_Figura 1.1: Diagrama de bloques_

### Comparativa prodcutos del mercado

Dado que el proyecto resuelve un problema demasiado específico, no existe un producto rápidamente disponible en el mercado. Ademas cabe destacar que este proyecto se basa en un prototipo que en su primer objetivo es mas academico y no tanto de mercado.

| Característica         | Park Assist                           | Cleverciti                              |
|------------------------|-------------------------------------------|-------------------------------------------|
| Reservas en Línea      | Sí                                        | Si                                        |
| Verificación de Disponibilidad en el Lugar         | Sí                                        | Si                                        |
| Guía Visual | Sí                                        | Si                                        |
| Control de Acceso               | Códigos QR o sistemas de identificación por matrícula          | Códigos QR o sistemas de identificación por matrícula   |
| Precio           | $10,000 y $50,000 USD                               | $20,000 a $60,000 USD                                 |

_Tabla 2: Comparación entre dos productos de medición de precipitaciones disponibles en el mercado_

### Requerimientos 
La Tabla 3 presenta los requerimientos del proyecto.


| Grupo de Requerimiento         | ID de Requerimiento                       | Descripción                                                                                                                                                                                                   |
|--------------------------------|-------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Monitoreo                        | 1.1                                       | El sistema debe mostrar la disponibilidad de espacios en tiempo real como asi tambien en la app.                                                                                                                                                |
| Monitoreo                        | 1.2                                       | El sistema debe permitir al propietario monitorear el sistema mediante una conexión UART a una PC.                                                                                                                                               |
| Conectividad                         | 2.1                                       |El sistema debe permitir a los usuarios realizar reservas de espacios de estacionamiento a través de una aplicación o página web mediante WiFi.                                                                                                                              |
| Conectividad                   | 2.2                                       | El sistema debe permitir al propietario monitorear y controlar el sistema mediante una conexión UART a una PC.                                                                                                                                                              |
| Mecánica                   | 3.1                                       | El sistema debe controlar un motor servo que simula una barrera, la cual se abrirá o cerrará en función de la validación de la reserva o la disponibilidad de espacios.                                                                                                 |
| Configuración                       | 4.1                                       |  El sistema debe proporcionar a los usuarios un código único para cada reserva, que se utilizará para acceder al estacionamiento.                                                                                                                                                      |
| Configuración                       | 4.2                                       |  El sistema debe ser escalable para permitir la integración de más funcionalidades en el futuro, como la gestión de pagos o la expansión a más espacios de estacionamiento.                                                                                              |
| Configuración                   | 4.3                                       | La interfaz de usuario debe ser fácil de usar e intuitiva, tanto en la aplicación/web como en la pantalla LCD del estacionamiento.                                                                                                                                                                   |
| Tiempo de Ejecución                   | 5.1                                       | El proyecto se entregará antes del 17 de Septiembre de 2024.                                                                                                                                           |
| Manual de uso y Documentación                   | 6.1                                       | El código del sistema embebido estará disponible en un repositorio git, acompañado de un informe detallado con lista de partes, diagramas de conexión, requerimientos cumplidos, forma de uso y conclusiones.                                                                                                    |
| Costo                  | 7.1                                       | El costo del dispositivo será menor a los 50 dólares.                                                                               

_Tabla 3: Requerimientos del sistema_


### Casos de uso

### Caso 1 - Reservar un Espacio de Estacionamiento

| Elemento de Caso de Uso | Definición                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|-------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Disparador              |El usuario desea reservar un espacio de estacionamiento antes de llegar al lugar.                                                                                                                                                                                                                                                                                                                                                           |
| Precondición            | El usuario tiene acceso a la aplicación o página web del sistema y está autenticado.                                                                                                                                                                                                                                                                                                                                                            |
| Flujo Básico            | El usuario abre la aplicación del servidor.El sistema muestra la disponibilidad de lugares. El usuario reserva el lugar y el sistema le brinda un codigo.                                                                                                                                                                                                                                                                                                   |
| Flujo Alternativo | Si el usuario intenta reservar un espacio que ya está ocupado, el sistema muestra un mensaje de error y permite seleccionar otro espacio. |

_Tabla 4: Caso de uso número 1_

### Caso 2 - Verificar Disponibilidad de Espacios en el Estacionamiento

| Elemento de Caso de Uso | Definición                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|-------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Disparador              |El usuario desea verificar la disponibilidad de espacios en el estacionamiento al llegar al lugar.                                                                                                                                                                                                                                                                                                                                                           |
| Precondición            | 	El usuario está físicamente en el estacionamiento y puede ver el display LCD.                                                                                                                                                                                                                                                                                                                                                            |
| Flujo Básico            |El usuario consulta la disponibilidad en el display LCD ubicado en el estacionamiento.El sistema muestra el número de espacios disponibles en tiempo real.El usuario selecciona un boton definido en el teclado e ingresa al lugar.                                                                                                                                                                                                                                                                                                   |
| Flujo Alternativo | Si no hay espacios disponibles, el sistema muestra un mensaje indicando que el estacionamiento está lleno. |

_Tabla 5: Caso de uso número 2_

### Caso 3 - Control y Monitoreo del Sistema desde la PC

| Elemento de Caso de Uso | Definición                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|-------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Disparador              |El propietario o administrador del estacionamiento desea monitorear o controlar el sistema desde una PC.                                                                                                                                                                                                                                                                                                                                                           |
| Precondición            | El sistema está conectado a una PC mediante UART, y el propietario tiene acceso autorizado a la PC.                                                                                                                                                                                                                                                                                                                                                            |
| Flujo Básico            |El propietario accede a la interfaz de control en la PC.El sistema muestra el estado actual del estacionamiento, incluyendo la disponibilidad de espacios y el estado de la barrera. El propietario puede realizar acciones de control, como abrir o cerrar la barrera, o actualizar manualmente el estado de la disponibilidad.El sistema responde a las acciones del propietario en tiempo real.                                                                                                                                                                                                                                                                                                   |
| Flujo Alternativo | Si la conexión UART falla, el sistema muestra un mensaje de error en la PC y deshabilita las acciones de control remoto hasta que se restablezca la conexión. Si el propietario intenta realizar una acción no permitida o fuera de su autorización, el sistema rechaza la operación y muestra un mensaje de advertencia. |

_Tabla 6: Caso de uso número 3_

