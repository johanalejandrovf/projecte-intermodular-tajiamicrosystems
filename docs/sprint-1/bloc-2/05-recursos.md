# Selección de recursos materiales y humanos

## 1. Equipos cliente

| Equipo | Cantidad | Función | Requisitos principales |
|--------|----------|---------|------------------------|
| Ordenador de sobremesa | 2 | Dirección | i5, 16 GB RAM, SSD 512 GB, Windows 11 Pro |
| Ordenador de sobremesa | 4 | Gestión | i5, 16 GB RAM, SSD 512 GB, Windows 11 Pro |
| Ordenador de sobremesa | 6 | Taller | i5, 16 GB RAM, SSD 512 GB, virtualización activada |
| Ordenador de sobremesa | 4 | Desarrollo web | i5, 16 GB RAM, SSD 512 GB, dos salidas de vídeo |
| Ordenador de sobremesa | 8 | Implantación | i5, 16 GB RAM, SSD 512 GB, puerto RJ45 |
| **Total** | **24** | | |

**Justificación:** un ordenador por trabajador. Elegimos el mismo modelo para los cinco departamentos porque simplifica el mantenimiento, las piezas de repuesto y la instalación, y porque abarata la compra al pedir 24 unidades iguales. Los 16 GB de RAM permiten que el Taller levante máquinas virtuales para preparar los sistemas de los clientes. Todos llevan Windows 11 Pro, que es la versión que permite unirse al dominio.

## 2. Servidores

| Servidor | Cantidad | Función | Requisitos principales |
|----------|----------|---------|------------------------|
| Servidor de dominio | 1 | Usuarios, permisos y DNS interno | i5, 16 GB RAM, SSD 512 GB, Windows Server |
| NAS de copias | 1 | Carpetas compartidas y copias de seguridad | 4 bahías, RAID, montaje en rack |
| Servidor web (DMZ) | 1 | Web corporativa y servicios online | 8 GB RAM, Ubuntu Server |
| Servidor de correo (DMZ) | 1 | Correo de la empresa | 8 GB RAM, Ubuntu Server |

**Justificación:** separamos los servicios públicos de los internos, que es lo que exige la DMZ. El dominio y el NAS se quedan en la red interna porque guardan los datos de clientes y no deben verse desde Internet. Los dos servidores de la DMZ se virtualizan sobre un mismo equipo físico, porque la carga de una empresa de 24 trabajadores no justifica dos máquinas. El NAS lleva los discos en RAID para que una avería de un disco no pare la empresa.

## 3. Dispositivos de red

| Dispositivo | Cantidad | Función | Requisitos principales |
|-------------|----------|---------|------------------------|
| Router | 1 | Salida a Internet | Fibra. En el entorno de pruebas lo aporta VirtualBox |
| Firewall | 1 | Separar WAN, LAN y DMZ | 3 interfaces de red, NAT, VPN, reglas por zona |
| Switch | 1 | Conectar la red interna | 32 puertos Gigabit, gestionable, montaje en rack |
| SAI | 1 | Mantener encendidos los equipos críticos | 1500 VA, montaje en rack, apagado automático |
| Armario rack | 1 | Alojar firewall, switch, NAS y SAI | 12U, con llave y ventilación |

**Justificación:** el firewall necesita tres interfaces porque tiene que separar tres zonas; es la pieza clave del diseño. El switch de 32 puertos cubre los 29 equipos actuales y deja 3 libres; al ser gestionable podemos ver el estado de cada puerto y, si la empresa creciera, separar departamentos en VLAN sin cambiar el cableado. El SAI protege solo lo crítico (firewall, switch, servidor y NAS), no los puestos de trabajo, porque ahí el corte de luz no provoca pérdida de datos importante.

## 4. Otros equipos

| Equipo | Cantidad | Función |
|--------|----------|---------|
| Impresora multifunción de red | 2 | Impresión, copia y escaneo para Gestión y para Taller |
| Cableado estructurado Cat 6 | 29 tomas | Conectar cada puesto al switch |

**Justificación:** dos impresoras en red, una en cada zona de la oficina, es suficiente para 24 personas y evita tener una impresora por mesa. Cat 6 porque da Gigabit sin problemas y es el estándar actual en instalaciones nuevas.

## 5. Sistemas operativos

| Sistema | Cantidad | Dónde | Requisitos principales |
|---------|----------|-------|------------------------|
| Windows 11 Pro | 24 | Equipos cliente | 4 GB RAM mínimo, TPM 2.0. Incluido con los equipos |
| Windows Server 2025 Standard | 1 | Servidor de dominio | 2 GB RAM mínimo, 32 GB de disco |
| Ubuntu Server 24.04 LTS | 2 | Servidores web y de correo | 2 GB RAM mínimo, 25 GB de disco |
| Synology DSM | 1 | NAS | Incluido con el equipo |

**Justificación:** Windows 11 Pro es necesario para unir los equipos al dominio, y viene incluido en el precio de los ordenadores. Windows Server trae Active Directory y DNS, que es justo lo que necesitamos para centralizar usuarios. Ubuntu Server es gratuito, tiene soporte de cinco años y es el sistema más documentado para servidores web y de correo, lo que reduce el coste de licencias y el tiempo de puesta en marcha.

## 6. Aplicaciones

| Aplicación | Cantidad | Departamento | Función |
|------------|----------|--------------|---------|
| Microsoft 365 Empresa | 24 | Todos | Correo, ofimática y almacenamiento |
| Programa de gestión (ERP/CRM) | 6 | Dirección y Gestión | Clientes, citas, presupuestos y facturas |
| Wireshark y Cisco Packet Tracer | 14 | Taller e Implantación | Analizar y configurar redes |
| VirtualBox | 6 | Taller | Probar sistemas antes de instalarlos |
| Visual Studio Code y Git | 4 | Desarrollo web | Programar y controlar versiones |
| Apache y Postfix | 2 | Servidores de la DMZ | Servidor web y servidor de correo |
| Microsoft Defender para Empresas | 24 | Todos | Antivirus y protección de los equipos |
| Hyper Backup | 1 | NAS | Copias automáticas, locales y en la nube |

**Justificación:** cada departamento tiene solo las aplicaciones que necesita, lo que evita pagar licencias de más. Una buena parte son gratuitas (Wireshark, Packet Tracer, VirtualBox, VS Code, Git, Apache, Postfix), lo que abarata mucho el apartado de software. Hyper Backup viene incluido con el NAS y es el que permite la copia híbrida descrita en `02-alternatives-viabilitat.md`.

## 7. Recursos humanos para la implantación

Estas personas montan la infraestructura. Forman un **equipo de proyecto temporal**: trabajan en la implantación mientras dura y después vuelven a su puesto habitual.

| Perfil | Personas | Responsabilidades generales |
|--------|----------|-----------------------------|
| Jefe de proyecto | 1 | Planificar el trabajo, repartir tareas, controlar plazos y presupuesto, y hablar con la dirección |
| Técnico de cableado | 2 | Tender el cableado, montar las tomas de red y el armario rack, y certificar cada punto |
| Técnico de redes y seguridad | 1 | Configurar el router, el firewall, la DMZ, el switch, el NAT y las reglas de filtrado |
| Administrador de sistemas | 1 | Instalar los servidores, crear el dominio, los usuarios y las carpetas compartidas, y dejar las copias funcionando |
| Técnico de soporte y formación | 1 | Preparar e instalar los 24 equipos cliente, migrar los datos antiguos y formar a los trabajadores |
| **Total** | **6** | |

## 8. Diferencia con los trabajadores ordinarios

| | Equipo de implantación | Trabajadores ordinarios |
|---|---|---|
| Quiénes son | Las 6 personas de la tabla anterior | Los 24 trabajadores de la empresa |
| Qué hacen | **Montan y ponen en marcha** la infraestructura | **Usan** la infraestructura una vez montada |
| Duración | Temporal: terminan cuando todo funciona | Permanente |
| Objetivo | Entregar la red funcionando y documentada | Su trabajo diario en su departamento |
| Relación con el proyecto | Lo ejecutan | Reciben formación y soporte |

Cuando termine la implantación, **el mantenimiento diario pasa a los trabajadores ordinarios del departamento de Taller**, que ya cuenta con administradores de sistemas y técnicos de soporte. No hace falta contratar personal nuevo de forma permanente.

Algunos miembros del equipo de implantación salen de la propia plantilla (Implantación y Taller tienen el perfil necesario), lo que reduce el coste y hace que quien monta la red sea quien después la mantiene.