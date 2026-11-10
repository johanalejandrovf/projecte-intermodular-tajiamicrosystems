# Partes del proyecto y organización con Scrum y Trello

**Empresa:** Tajia Microsystems S.L.
**Proyecto:** implantación de una infraestructura informática segura (equipos, servidores, red, sistemas y servicios).

---

## 1. Partes principales del proyecto

El proyecto se divide en cinco partes, que se hacen en este orden aunque algunas se solapan:

| Parte | Objetivo | Documentos / resultado |
|---|---|---|
| **1. Análisis** | Entender qué necesita cada departamento y si las soluciones son viables técnica y económicamente. | `01-necessitats.md`, `02-alternatives-viabilitat.md` |
| **2. Diseño** | Definir cómo será la infraestructura: red, direccionamiento IP, recursos materiales y humanos, y presupuesto. | `03-disseny-xarxa.md`, `04-adrecament-ip.md`, `05-recursos.md`, `06-pressupost.md` |
| **3. Implantación** | Montar y configurar la infraestructura: cableado, red, servidores, sistemas operativos, usuarios, servicios y copias de seguridad. | Servidores y servicios funcionando |
| **4. Pruebas** | Comprobar que todo funciona y es seguro: conectividad entre VLAN, acceso remoto, permisos de usuarios, restauración de copias y cortes de corriente. | Registro de pruebas y fallos corregidos |
| **5. Documentación** | Dejar por escrito el proyecto, de forma que otra persona pueda entenderlo y mantenerlo: manuales, diagramas, contraseñas guardadas de forma segura y procedimientos. | `README.md`, ficheros `.md` e imágenes en `img/` |

---

## 2. Organización con Scrum

Trabajamos con **Scrum**, una forma de organizar el trabajo en periodos cortos (*sprints*) con tareas pequeñas que se revisan con frecuencia.

| Concepto de Scrum | Cómo lo aplicamos en el proyecto |
|---|---|
| **Product Owner** | Persona que decide qué es lo más importante (en esta actividad, el profesorado y las necesidades de la empresa). |
| **Scrum Master** | Integrante del equipo que cuida que se siga el método y quita obstáculos. Rota cada sprint. |
| **Equipo de desarrollo** | Los integrantes del grupo, que se reparten las tareas. |
| **Product Backlog** | Lista de todas las tareas del proyecto (lista *Pendiente* de Trello). |
| **Sprint** | Periodo de trabajo con un objetivo. **Sprint 1** = Bloque 2 (planteamiento de soluciones TIC). |
| **Reunión diaria / de equipo** | Revisión corta del tablero: qué hice, qué haré y qué me bloquea. |
| **Revisión y retrospectiva** | Al final del sprint se enseña lo hecho y se decide qué mejorar. |

---

## 3. Tablero de Trello

- **Enlace al tablero (accesible para el profesorado):** `COMPLETAR → https://trello.com/b/XXXXXXXX/tajia-microsystems`
  *(Compartir el tablero con el profesorado como «Observador/a» o hacerlo visible para quien tenga el enlace.)*

![Captura del tablero de Trello](img/trello-tablero.png)

> **COMPLETAR antes de entregar:** guardar una captura del tablero en `img/trello-tablero.png`.

### Listas del tablero

| Lista | Significado |
|---|---|
| **Pendiente** | Tareas que aún no han empezado. |
| **En proceso** | Tareas en las que alguien está trabajando ahora. |
| **Finalizado** | Tareas terminadas y revisadas. |

### Etiquetas (colores)

Una etiqueta por cada parte del proyecto: Análisis, Diseño, Implantación, Pruebas y Documentación.

### Tarjetas del tablero

Cada tarjeta tiene un responsable y una breve descripción. Los nombres de los integrantes se escriben en la columna *Responsable* (aquí aparecen como Integrante 1, 2, 3...).

| Nº | Tarjeta | Parte | Responsable | Breve descripción | Lista inicial |
|---:|---|---|---|---|---|
| 1 | Necesidades por departamento | Análisis | Integrante 1 | Tabla con las necesidades de cada departamento, usuarios afectados y justificación. | Finalizado |
| 2 | Alternativas y viabilidad | Análisis | Integrante 2 | Comparar soluciones posibles y elegir la más viable técnica y económicamente. | Finalizado |
| 3 | Diseño de la red | Diseño | Integrante 3 | Esquema de red con VLAN, switches, firewall y zona DMZ. | En proceso |
| 4 | Direccionamiento IP | Diseño | Integrante 1 | Plan de direcciones IP y subredes por departamento. | En proceso |
| 5 | Recursos materiales y humanos | Diseño | Integrante 2 | Equipos, servidores, red, sistemas, aplicaciones y equipo de implantación. | Finalizado |
| 6 | Presupuesto económico | Diseño | Integrante 3 | Presupuesto con precios reales, licencias, IVA y justificación. | Finalizado |
| 7 | Planificación con Scrum y Trello | Diseño | Integrante 1 | Partes del proyecto, tablero de Trello y tarjetas. | En proceso |
| 8 | Cableado y rack | Implantación | Integrante 2 | Tirar cable, instalar tomas y montar el rack. | Pendiente |
| 9 | Configuración de router, firewall y switches | Implantación | Integrante 3 | VLAN, rutas, VPN, reglas del firewall y DMZ. | Pendiente |
| 10 | Servidor de dominio | Implantación | Integrante 1 | Windows Server con Active Directory, DNS y DHCP. | Pendiente |
| 11 | Servidor de ficheros y permisos | Implantación | Integrante 2 | Carpetas compartidas por departamento con permisos. | Pendiente |
| 12 | Servidores Ubuntu (web, base de datos, correo) | Implantación | Integrante 3 | Instalar y configurar los tres servicios. | Pendiente |
| 13 | Copias de seguridad (Veeam) | Implantación | Integrante 1 | Programar copias de los servidores y probar la restauración. | Pendiente |
| 14 | Instalación de equipos cliente y antivirus | Implantación | Integrante 2 | Instalar Windows 11, unir al dominio y desplegar antivirus y aplicaciones. | Pendiente |
| 15 | Pruebas de red y seguridad | Pruebas | Integrante 3 | Comprobar VLAN, firewall, VPN y acceso a los servicios. | Pendiente |
| 16 | Pruebas de servicios y copias | Pruebas | Integrante 1 | Comprobar usuarios, permisos y restauración de copias. | Pendiente |
| 17 | Documentación final y README | Documentación | Integrante 2 | Manuales, diagramas, enlaces y revisión final del repositorio. | Pendiente |

---

## 4. Cómo se relaciona el tablero con las partes del proyecto

La planificación de Trello es una herramienta de organización. Para evaluar el CE RA2.f lo que cuenta es que cada parte del proyecto esté explicada:

- **Análisis y Diseño** (tarjetas 1-7) están hechas en este bloque: los ficheros de `docs/sprint-1/bloc-2/` los documentan.
- **Implantación, Pruebas y Documentación** (tarjetas 8-17) se planifican para los siguientes sprints. Cada tarjeta tiene responsable y descripción, así que se sabe quién hace qué y qué se espera.
- Cuando una tarjeta cambia de lista, el tablero refleja el avance real del proyecto.