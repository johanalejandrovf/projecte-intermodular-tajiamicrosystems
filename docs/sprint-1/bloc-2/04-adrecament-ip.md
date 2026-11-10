# Diseño de la infraestructura y diagrama de red

## Diagrama de red

![Diagrama de red de Tajia Microsystems S.L.](../../../img/diagrama-red.png)

## Zonas de la red

La red está dividida en tres zonas separadas por el firewall.

| Zona | Qué contiene | ¿Se ve desde Internet? |
|------|--------------|------------------------|
| Internet | La conexión de fibra | - |
| DMZ | Servidor web y servidor de correo | Sí |
| Red interna (LAN) | Servidores internos, ordenadores e impresoras | No |

## Funciones de los componentes

| Componente | Función |
|------------|---------|
| Router | Conecta la empresa a Internet por fibra |
| Servidor de comunicaciones (firewall) | Separa las tres zonas, hace NAT y da acceso VPN |
| Servidor web | Aloja la web y los servicios para clientes |
| Servidor de correo | Envía y recibe el correo de la empresa |
| Switch principal | Une toda la red interna y comunica las VLAN |
| Switches de acceso | Conectan los ordenadores y las impresoras |
| Puntos de acceso Wi-Fi | Dan cobertura Wi-Fi a los portátiles |
| Servidor de dominio | Usuarios, contraseñas, DNS y DHCP |
| Servidor de ficheros | Carpetas compartidas y copias de seguridad |
| Servidor de base de datos | Datos de clientes, citas y facturas |
| SAI | Mantiene encendidos los servidores y la red si se va la luz |

## Conexiones

- El **router** se conecta al **firewall**, que tiene un puerto para la **DMZ** y otro para la **red interna**.
- El **firewall** se conecta al **switch principal**.
- Del **switch principal** cuelgan los **servidores internos** y los **2 switches de acceso**.
- De los **switches de acceso** cuelgan los ordenadores, las impresoras y los puntos de acceso Wi-Fi.
- Los **portátiles de Implantación** se conectan por Wi-Fi en la oficina y por VPN desde casa del cliente.

## VLAN

| VLAN | Departamento |
|------|--------------|
| 10 | Dirección |
| 20 | Gestión |
| 30 | Implantación |
| 40 | Taller |
| 50 | Desarrollo web |
| 60 | Servidores |
| 70 | Invitados |

## Decisiones técnicas

- **Topología en estrella:** todo se conecta al switch principal. Es fácil de ampliar y, si falla un cable, solo afecta a un equipo.
- **Una VLAN por departamento:** aunque compartan switch, cada departamento está separado. Así un problema en uno no afecta a los demás.
- **Switch principal de nivel 3:** es el que comunica las VLAN entre sí y hace de puerta de enlace.
- **Red de invitados aparte:** los visitantes tienen Internet pero no entran en la red de la empresa.
- **VPN:** los técnicos de Implantación se conectan de forma segura desde casa del cliente.
- **SAI:** protege los servidores, el firewall y los switches de los cortes de luz.

## Servicios en la DMZ

| Servicio | Por qué está en la DMZ |
|----------|------------------------|
| Servidor web | Los clientes entran desde Internet a la web y a los servicios online |
| Servidor de correo | Tiene que recibir correos de fuera de la empresa |

Están en la DMZ porque tienen que ser accesibles desde Internet. Si alguien los ataca, el firewall impide que llegue a la red interna, donde están los datos de clientes, los ficheros y los usuarios. Por eso el dominio, los ficheros y la base de datos están en la red interna y no se ven desde fuera.

## Fuentes técnicas consultadas

- Cisco Networking Academy: temario de CCNA sobre VLAN, switching y diseño de redes.
- Documentación de pfSense (Netgate) sobre firewall, DMZ y VPN.
- Documentación de Microsoft sobre Active Directory, DNS y DHCP en Windows Server.
- Documentación de Ubuntu Server sobre servidores web y de correo.
- Documentos del Bloque 1 y el `05-recursos.md` del proyecto.