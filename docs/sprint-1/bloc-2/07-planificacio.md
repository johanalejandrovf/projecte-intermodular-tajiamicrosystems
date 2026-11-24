# Partes del proyecto y organización con Scrum y Trello

## 1. Partes principales del proyecto

El proyecto se divide en cinco partes. Cada una tiene un objetivo propio y entrega algo concreto que permite empezar la siguiente.

| Parte | Objetivo | Qué entrega |
|-------|----------|-------------|
| Análisis | Entender qué necesita la empresa antes de decidir nada | Tabla de necesidades por departamento y fuentes consultadas |
| Diseño | Decidir cómo va a ser la solución y justificarla | Alternativas, diagrama de red, plan de direcciones, recursos y presupuesto |
| Implantación | Montar lo diseñado y ponerlo en marcha | Red funcionando: sistemas instalados, dominio, DMZ y servicios |
| Pruebas | Comprobar que todo funciona y es seguro | Informe de pruebas de conectividad, servicios, accesos y aislamiento |
| Documentación | Dejar constancia de lo hecho y poder defenderlo | Documentación final y presentación del proyecto |

### Análisis

Partimos de la empresa definida en el Bloque 1 y averiguamos qué necesita de verdad cada departamento: conectividad, acceso a Internet, compartición de ficheros, impresión, cuentas de usuario, web corporativa y seguridad. Sin esta parte, el diseño se haría a ciegas. El resultado está en `01-necessitats.md`.

### Diseño

Es la parte en la que estamos. Se proponen alternativas, se estudia su viabilidad y se elige una; se dibuja la topología de red con su DMZ; se reparten las direcciones IP y los nombres de los equipos; se eligen los recursos materiales y humanos; y se calcula el presupuesto. Nada se instala todavía: lo que se entrega son documentos que permiten decidir y, después, ejecutar.

### Implantación

Se monta lo diseñado: máquinas virtuales, sistemas operativos de clientes y servidores, nombres y direcciones, servidor de comunicaciones, red interna, DMZ, enrutamiento entre redes y servicios de red. Es la parte más larga del proyecto y ocupa varios sprints.

### Pruebas

Se comprueba que la infraestructura hace lo que tenía que hacer: que hay conectividad entre departamentos, que los servicios responden, que se puede acceder desde fuera a lo publicado en la DMZ y, sobre todo, que **desde la DMZ no se llega a la red interna**. Las incidencias que aparecen se corrigen aquí.

### Documentación

Se recoge todo lo hecho en un documento final y se prepara la presentación y defensa. Incluye manuales de configuración, el plan de direcciones definitivo y las pruebas realizadas.

## 2. Metodología Scrum

Trabajamos por **sprints**: bloques de trabajo con un plazo fijo y un conjunto de tareas cerrado. Al terminar cada sprint se revisa lo hecho antes de pasar al siguiente.

| Elemento de Scrum | Cómo lo aplicamos |
|-------------------|-------------------|
| Product Backlog | Lista de todas las tareas del proyecto, sacadas del guion de los sprints |
| Sprint Backlog | Las tarjetas de cada tablero de Trello, una por tarea del sprint |
| Sprint | Cada uno de los siete bloques del proyecto, de 4 o 5 semanas |
| Sprint Planning | Al empezar el sprint repartimos las tarjetas y ponemos responsable y fecha |
| Daily | Al empezar cada sesión repasamos en qué está cada uno y qué bloquea |
| Sprint Review | Al cerrar el sprint comprobamos que las tarjetas están realmente terminadas |
| Retrospectiva | Anotamos qué ha funcionado y qué cambiamos para el sprint siguiente |

Los roles los repartimos entre los dos miembros del equipo: uno hace de responsable de organización (seguimiento del tablero y de los plazos) y el otro de responsable técnico, y ambos ejecutan tareas.

## 3. Organización en Trello

Hemos creado **un tablero por sprint**, con las mismas tres listas en todos:

| Lista en nuestro tablero | Equivale a |
|--------------------------|------------|
| PER FER | Pendiente |
| FENT-SE | En proceso |
| FETES | Finalizado |

Cada tarjeta es una tarea del sprint y lleva:

- **Título**: el nombre de la tarea, numerado para mantener el orden.
- **Descripción**: el objetivo de la tarea y lo que hay que entregar.
- **Estimación**: las horas previstas.
- **Fecha de vencimiento**: la semana en la que debe estar terminada.
- **Responsable**: el miembro del equipo que la ejecuta.

Una tarea avanza de izquierda a derecha: nace en PER FER, pasa a FENT-SE cuando alguien empieza a trabajar en ella y llega a FETES cuando está terminada y revisada por el compañero.

### Enlaces a los tableros

| Sprint | Enlace |
|--------|--------|
| Sprint 1 – Definició, disseny i planificació | https://trello.com/b/nkEzwG5J |
| Sprint 2 – Implantació de la infraestructura | https://trello.com/b/hIUOfHmW |
| Sprint 3 – Centralització, usuaris i recursos compartits | https://trello.com/b/vqWMAVcp |
| Sprint 4 – Serveis de xarxa i accés remot | https://trello.com/b/weBje2Y8 |
| Sprint 5 – Serveis web i seguretat | https://trello.com/b/qDmHFp6U |
| Sprint 6 – Investigació i ampliació de la infraestructura | https://trello.com/b/zOe6pNXo |
| Sprint 7 – Integració, documentació i validació final | https://trello.com/b/Nw6jmfLx |

### Captura del tablero

![Tablero de Trello del Sprint 1](../../../img/trello-sprint-1.png)

## 4. Estado actual del proyecto

| Sprint | Estado |
|--------|--------|
| Sprint 1 – Definición, diseño y planificación | En curso. Todas las tareas terminadas salvo el diagrama de red, que está en FENT-SE |
| Sprints 2 a 7 | Pendientes. Todas las tarjetas en PER FER |

## 5. Reparto del trabajo

| Tarea del Bloque 2 | Responsable |
|--------------------|-------------|
| 01 – Necesidades TIC | |
| 02 – Alternativas y viabilidad | |
| 03 – Diseño de la red y diagrama | |
| 04 – Direccionamiento IP y nombres | |
| 05 – Selección de recursos | |
| 06 – Presupuesto | |
| 07 – Planificación y Trello | |