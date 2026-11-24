# Identificación de las necesidades TIC

## Departamentos y trabajadores

| Departamento | Trabajadores | Equipos |
|--------------|--------------|---------|
| Dirección | 2 | 2 ordenadores |
| Gestión | 4 | 4 ordenadores + 1 impresora |
| Taller | 6 | 6 ordenadores + 1 impresora |
| Desarrollo web | 4 | 4 ordenadores |
| Implantación | 8 | 8 ordenadores |
| **Total** | **24** | **24 ordenadores + 2 impresoras** |

## Necesidades comunes a toda la empresa

| Necesidad | Usuarios afectados | Justificación |
|-----------|--------------------|---------------|
| Conexión de red por cable | 24 | Todos los trabajadores usan un ordenador conectado a la red interna |
| Acceso a Internet | 24 | Correo, búsqueda de información y servicios online |
| Cuenta de usuario propia | 24 | Cada trabajador entra con su usuario y accede solo a lo que le corresponde |
| Correo electrónico corporativo | 24 | Comunicación con clientes, proveedores y compañeros |
| Carpetas compartidas | 24 | Trabajar sobre los mismos documentos sin enviarlos por correo |
| Copias de seguridad | 24 | Evitar la pérdida de documentos si falla un equipo |
| Seguridad perimetral (firewall) | 24 | La empresa maneja datos de clientes que hay que proteger |

## Necesidades por departamento

| Departamento | Necesidad | Usuarios afectados | Justificación |
|--------------|-----------|--------------------|---------------|
| Dirección | Acceso a la información de todos los departamentos | 2 | Necesitan consultar informes y datos de toda la empresa |
| Dirección | Acceso remoto seguro (VPN) | 2 | Se reúnen con clientes y proveedores fuera de la oficina |
| Gestión | Programa de gestión de clientes, citas y facturas | 4 | Organizan las citas y llevan la contabilidad |
| Gestión | Impresión y escaneo en red | 4 | Imprimen facturas, presupuestos y contratos |
| Gestión | Carpeta compartida del departamento | 4 | Trabajan sobre los mismos documentos de clientes |
| Taller | Equipos con capacidad para máquinas virtuales | 6 | Preparan y prueban servidores antes de instalarlos en el cliente |
| Taller | Acceso de administrador a los servidores | 6 | Se encargan del mantenimiento y de la seguridad de los sistemas |
| Taller | Impresión en red | 6 | Imprimen fichas de reparación e informes técnicos |
| Implantación | Herramientas de configuración de red | 8 | Configuran routers, switches y cableado en casa del cliente |
| Implantación | Acceso remoto seguro (VPN) | 8 | Necesitan llegar a los recursos de la empresa desde casa del cliente |
| Desarrollo web | Servidor web accesible desde Internet | 4 | Publican la web corporativa y los servicios online de los clientes |
| Desarrollo web | Herramientas de programación y control de versiones | 4 | Programan y mantienen las webs |
| Desarrollo web | Carpeta compartida del departamento | 4 | Comparten código, imágenes y diseños |

## Necesidades de la web corporativa y del correo

| Necesidad | Justificación |
|-----------|---------------|
| Servidor web publicado en Internet | Los clientes acceden a la web y a los servicios online desde fuera |
| Servidor de correo propio | La empresa necesita direcciones con su dominio y control del buzón |
| Aislamiento de los servicios públicos | Si atacan la web o el correo, el atacante no debe llegar a la red interna |

Esta última necesidad es la que obliga a montar una **DMZ**: una red aparte, separada por el firewall, donde se colocan los servidores que se ven desde Internet.

## Fuentes consultadas

- Documentos del Bloque 1 del proyecto: `01-empresa.md`, `02-organitzacio.md`, `03-recursos-tic.md`, `04-maquinari-programari.md` y `05-ods.md`.
- Organigrama de la empresa y relación de puestos de trabajo, para saber cuántos trabajadores hay en cada departamento y qué hace cada uno.
- Webs de empresas reales del mismo sector (Telefónica Tech y Sothis), para comparar qué servicios ofrecen a sus clientes.
- Documentación de los fabricantes sobre los requisitos de los sistemas elegidos: Microsoft (Windows 11 Pro y Windows Server) y Canonical (Ubuntu Server).
- Guía de la Agencia Española de Protección de Datos sobre medidas de seguridad en pymes, para las necesidades de protección de datos de clientes.