# Selección de recursos materiales y humanos

## Equipos cliente

| Equipo | Cantidad | Función | Requisitos |
|--------|----------|---------|------------|
| Portátil | 2 | Dirección | i5, 16 GB RAM, SSD 512 GB |
| Portátil | 9 | Implantación | i5, 16 GB RAM, puerto RJ45 |
| Sobremesa | 4 | Gestión | i5, 8 GB RAM, SSD 256 GB |
| Sobremesa | 8 | Taller | i7, 32 GB RAM, SSD 1 TB |
| Sobremesa | 4 | Desarrollo web | i7, 32 GB RAM, gráfica dedicada |

**Justificación:** cada trabajador necesita un ordenador. Dirección e Implantación usan portátiles porque trabajan fuera de la oficina. Taller tiene 2 equipos más para hacer pruebas. Taller y Desarrollo web necesitan más potencia para usar máquinas virtuales y programar.

## Servidores

| Servidor | Cantidad | Función | Requisitos |
|----------|----------|---------|------------|
| Dominio | 1 | Usuarios, DHCP y DNS | 16 GB RAM, RAID 1 |
| Ficheros | 1 | Documentos y copias | 16 GB RAM, 8 TB, RAID 5 |
| Web | 1 | Webs de los clientes | 32 GB RAM, RAID 1 |
| Base de datos | 1 | Clientes, citas y facturas | 32 GB RAM, RAID 10 |
| Correo | 1 | Correo de la empresa | 16 GB RAM, RAID 1 |

**Justificación:** separamos cada servicio en un servidor para que, si uno falla, el resto siga funcionando. Todos usan RAID para no perder datos si se estropea un disco.

## Dispositivos de red

| Dispositivo | Cantidad | Función | Requisitos |
|-------------|----------|---------|------------|
| Router | 1 | Salida a Internet | Fibra, VPN |
| Firewall | 1 | Proteger la red | VPN, DMZ |
| Switch principal | 1 | Unir toda la red | Nivel 3, VLAN, 10 Gb |
| Switch de acceso | 2 | Conectar los equipos | 24 puertos, PoE, VLAN |
| Punto de acceso | 2 | Wi-Fi | Wi-Fi 6, PoE, WPA3 |
| SAI | 1 | Evitar apagones | 3000 VA |

**Justificación:** el firewall protege los datos de los clientes. Los switches permiten separar los departamentos en VLAN, y el PoE da corriente a los puntos de acceso por el mismo cable. El SAI mantiene encendidos los servidores si se va la luz.

## Sistemas operativos

| Sistema | Cantidad | Dónde | Requisitos |
|---------|----------|-------|------------|
| Windows 11 Pro | 27 | Equipos cliente | 4 GB RAM, TPM 2.0 |
| Windows Server 2025 | 2 | Dominio y ficheros | 2 GB RAM, 32 GB disco |
| Ubuntu Server 24.04 | 3 | Web, base de datos y correo | 2 GB RAM, 25 GB disco |

**Justificación:** Windows 11 Pro permite unir los equipos al dominio. Windows Server incluye Active Directory, DNS y DHCP. Ubuntu Server es gratuito y muy usado para servicios web.

## Aplicaciones

| Aplicación | Cantidad | Departamento | Función |
|------------|----------|--------------|---------|
| Microsoft 365 | 25 | Todos | Ofimática y correo |
| Programa de gestión | 6 | Dirección y Gestión | Clientes, citas y facturas |
| Packet Tracer y Wireshark | 17 | Implantación y Taller | Configurar y revisar redes |
| VirtualBox | 8 | Taller | Máquinas virtuales |
| VS Code y Git | 4 | Desarrollo web | Programar webs |
| Antivirus | 32 | Todos | Proteger los equipos |
| Veeam | 5 | Servidores | Copias de seguridad |

**Justificación:** cada departamento tiene las aplicaciones que necesita para su trabajo. Muchas son gratuitas, lo que ahorra dinero. El antivirus y las copias protegen los datos de los clientes.

## Equipo de implantación

| Perfil | Personas | Responsabilidades |
|--------|----------|-------------------|
| Jefe de proyecto | 1 | Planificar y controlar el trabajo |
| Técnico de cableado | 2 | Cableado, tomas y rack |
| Técnico de redes y seguridad | 1 | Router, firewall, switches, Wi-Fi y antivirus |
| Administrador de sistemas | 1 | Servidores, usuarios y copias |
| Técnico de soporte | 1 | Instalar equipos y formar a los usuarios |

## Diferencia con los trabajadores ordinarios

- **Equipo de implantación:** son 6 personas que montan la infraestructura. Es un equipo temporal y termina cuando todo funciona.
- **Trabajadores ordinarios:** son los 25 trabajadores de la empresa. Solo usan la infraestructura una vez montada y reciben formación para usarla.