# Presupuesto económico

**Empresa:** Tajia Microsystems S.L.
**Base:** documento de recursos materiales y humanos (`05-recursos.md`).
**Moneda:** euros (€). **Todos los importes de las tablas son SIN IVA** (IVA aplicable: 21 %). Al final se calcula el total con IVA.

> **Aviso sobre los precios.** Son precios de referencia de tiendas y fabricantes consultados en noviembre de 2026. Cuando la tienda mostraba el precio con IVA, se ha convertido a base imponible dividiendo entre 1,21. Los precios de hardware varían mucho de un día a otro, así que conviene volver a comprobarlos antes de comprar. Cada fila lleva el número de la fuente (ver sección *Fuentes*).

---

## 1. Equipos cliente

Todos los equipos incluyen **Windows 11 Pro preinstalado** (licencia OEM incluida en el precio), por eso la fila de Windows 11 Pro de la sección 4 vale 0 €.

| Descripción | Dpto. | Cant. | Precio unitario | Subtotal | Fuente |
|---|---|---:|---:|---:|:---:|
| Portátil Dell Pro 14 PC14250 (Core 5 120U, 16 GB, SSD 512 GB, Win 11 Pro) | Dirección | 2 | 725,75 € | 1.451,50 € | [1] |
| Portátil Dell Latitude 3550 15,6" (Core Ultra 5 125U, 16 GB, SSD 512 GB, RJ45, Win 11 Pro) | Implantación | 9 | 693,39 € | 6.240,51 € | [2] |
| PC sobremesa PcCom Work (i5-12400, 16 GB, SSD 500 GB, Win 11 Pro) | Gestión | 4 | 445,45 € | 1.781,80 € | [3] |
| PC sobremesa PcCom Work (i7-12700, 32 GB, SSD 1 TB, Win 11 Pro) | Taller | 8 | 652,07 € | 5.216,56 € | [4] |
| Estación Lenovo ThinkStation P2 (i7-14700, 32 GB, SSD 1 TB, RTX 4060, Win 11 Pro) | Desarrollo web | 4 | 1.652,07 € | 6.608,28 € | [4] |
| **Subtotal equipos cliente (27 equipos)** | | **27** | | **21.298,65 €** | |

## 2. Servidores

Cada servidor es físico y separado, como indica el documento de recursos. Los discos adicionales se compran aparte para formar el RAID pedido. Los servidores se compran **sin sistema operativo**; las licencias están en la sección 4.

| Descripción | Función | Cant. | Precio unitario | Subtotal | Fuente |
|---|---|---:|---:|---:|:---:|
| Dell PowerEdge T160 (Xeon E-2414, 16 GB, 2 TB HDD, sin SO) | Dominio | 1 | 916,53 € | 916,53 € | [5] |
| Disco Seagate IronWolf 2 TB (segundo disco, **RAID 1**) | Dominio | 1 | 122,12 € | 122,12 € | [6] |
| Dell PowerEdge T360 (Xeon E-2414, 16 GB, SSD 480 GB, sin SO) | Ficheros | 1 | 1.519,83 € | 1.519,83 € | [5] |
| Disco Seagate IronWolf Pro 4 TB (3 discos en **RAID 5** = 8 TB útiles) | Ficheros | 3 | 165,25 € | 495,75 € | [6] |
| Dell PowerEdge T160 (Xeon 6325P, 32 GB, SSD 480 GB, sin SO) | Web | 1 | 1.430,64 € | 1.430,64 € | [7] |
| SSD Kingston DC600M 480 GB (segundo disco, **RAID 1**) | Web | 1 | 161,99 € | 161,99 € | [8] |
| Dell PowerEdge T360 (Xeon 6325P, 32 GB ECC DDR5, SSD 480 GB, PERC H755, garantía 3 años) | Base de datos | 1 | 3.968,00 € | 3.968,00 € | [9] |
| SSD Kingston DC600M 480 GB (3 más, 4 discos en **RAID 10** = 960 GB útiles) | Base de datos | 3 | 161,99 € | 485,97 € | [8] |
| Dell PowerEdge T160 (Xeon E-2414, 16 GB, 2 TB HDD, sin SO) | Correo | 1 | 916,53 € | 916,53 € | [5] |
| Disco Seagate IronWolf 2 TB (segundo disco, **RAID 1**) | Correo | 1 | 122,12 € | 122,12 € | [6] |
| **Subtotal servidores (5 servidores)** | | | | **10.139,48 €** | |

## 3. Dispositivos de red y alimentación

| Descripción | Cant. | Precio unitario | Subtotal | Fuente |
|---|---:|---:|---:|:---:|
| Router MikroTik RB5009UG+S+IN (VPN, salida a fibra) | 1 | 176,86 € | 176,86 € | [10] |
| Firewall Fortinet FortiGate 70F con licencia UTP + FortiCare de 1 año (VPN, DMZ) | 1 | 1.461,00 € | 1.461,00 € | [11] |
| Switch principal Ubiquiti USW-Pro-Aggregation (nivel 3, VLAN, 10 Gb SFP+) | 1 | 869,68 € | 869,68 € | [12] |
| Switch de acceso Ubiquiti USW-Pro-24-POE (24 puertos, PoE, VLAN, 2 × 10G SFP+) | 2 | 623,70 € | 1.247,40 € | [13] |
| Punto de acceso Ubiquiti UniFi U6 Pro (Wi-Fi 6, PoE, WPA3) | 2 | 155,50 € | 311,00 € | [14] |
| SAI APC Smart-UPS SMT3000RMI2UC (3000 VA, rack 2U) | 1 | 2.701,40 € | 2.701,40 € | [15] |
| **Subtotal red y SAI** | | | **6.767,34 €** | |

## 4. Sistemas operativos, aplicaciones y suscripciones

Aquí están las licencias y suscripciones necesarias. Las que son de pago **anual** se marcan como *recurrentes*.

| Descripción | Cant. | Tipo | Precio unitario | Subtotal | Fuente |
|---|---:|---|---:|---:|:---:|
| Windows 11 Pro | 27 | Incluida en los equipos | 0,00 € | 0,00 € | [1]–[4] |
| Windows Server 2025 Standard, 16 núcleos OEM (Dominio y Ficheros) | 2 | Perpetua | 949,00 € | 1.898,00 € | [16] |
| Windows Server 2025 CAL de usuario (una por trabajador) | 25 | Perpetua | 54,00 € | 1.350,00 € | [17] |
| Ubuntu Server 24.04 LTS (Web, Base de datos y Correo) | 3 | Software libre | 0,00 € | 0,00 € | [18] |
| Microsoft 365 Empresa Estándar (12 meses × 20,36 €) | 25 | **Recurrente anual** | 244,32 € | 6.108,00 € | [19] |
| Programa de gestión: Odoo Standard (12 meses × 14,90 €) | 6 | **Recurrente anual** | 178,80 € | 1.072,80 € | [20] |
| Antivirus ESET PROTECT Entry (26-49 dispositivos, 1 año, equipos y servidores) | 32 | **Recurrente anual** | 23,99 € | 767,68 € | [21] |
| Veeam Data Platform Foundation (copias de seguridad, 1 año) | 5 | **Recurrente anual** | 133,30 € | 666,50 € | [22] |
| Cisco Packet Tracer, Wireshark, VirtualBox, VS Code y Git | 17 / 17 / 8 / 4 / 4 | Gratuitas | 0,00 € | 0,00 € | [23] |
| **Subtotal licencias y suscripciones** | | | | **11.862,98 €** | |

---

## 5. Resumen y total general

| Bloque | Importe sin IVA |
|---|---:|
| 1. Equipos cliente | 21.298,65 € |
| 2. Servidores | 10.139,48 € |
| 3. Red y SAI | 6.767,34 € |
| 4. Licencias y suscripciones | 11.862,98 € |
| **Base imponible** | **50.068,45 €** |
| IVA 21 % | 10.514,37 € |
| **TOTAL GENERAL (IVA incluido)** | **60.582,82 €** |

**Coste recurrente anual a partir del segundo año** (sin IVA): 9.218,73 €. Son Microsoft 365 (6.108,00 €), Odoo (1.072,80 €), ESET (767,68 €), Veeam (666,50 €) y la renovación de la licencia UTP del firewall (603,75 € [24]).

### ¿Los importes llevan IVA?

- **Sí se añade:** todas las tablas son **sin IVA** y el IVA (21 %) se suma solo en el total.
- Algunas tiendas mostraban el precio con IVA (PcComponentes, Estonia, etc.). Esos precios se han convertido a base imponible. El switch principal se vendía con IVA de Estonia (24 %), por eso se divide entre 1,24 y no entre 1,21.

---

## 6. Comprobación con el documento de recursos

| Elemento | Documento de recursos | Presupuesto | ¿Coincide? |
|---|---:|---:|:---:|
| Portátiles Dirección / Implantación | 2 / 9 | 2 / 9 | ✔ |
| Sobremesas Gestión / Taller / Desarrollo web | 4 / 8 / 4 | 4 / 8 / 4 | ✔ |
| Servidores (dominio, ficheros, web, BD, correo) | 5 | 5 | ✔ |
| Router / Firewall / Switch principal | 1 / 1 / 1 | 1 / 1 / 1 | ✔ |
| Switches de acceso / Puntos de acceso / SAI | 2 / 2 / 1 | 2 / 2 / 1 | ✔ |
| Windows 11 Pro / Windows Server / Ubuntu Server | 27 / 2 / 3 | 27 / 2 / 3 | ✔ |
| Microsoft 365 / Programa de gestión | 25 / 6 | 25 / 6 | ✔ |
| Packet Tracer y Wireshark / VirtualBox / VS Code y Git | 17 / 8 / 4 | 17 / 8 / 4 | ✔ |
| Antivirus / Veeam | 32 / 5 | 32 / 5 | ✔ |

Las cantidades de equipos, red y licencias coinciden con el documento de recursos. Las **líneas extra** (discos para el RAID y CAL de Windows Server) no cambian el número de equipos. Son componentes que exige la configuración pedida: RAID 1, RAID 5 y RAID 10, y una CAL por usuario.

---

## 7. Justificación de las principales decisiones

1. **Marcas y modelos empresariales.** Se eligen Dell y Lenovo en portátiles, servidores y estaciones porque dan garantía y soporte profesional. En los sobremesas de Gestión y Taller se usa el PcCom Work, que cumple los requisitos con buena relación precio/prestaciones.
2. **Portátiles de Implantación con RJ45.** El documento de recursos exige puerto RJ45, porque el equipo configura redes y servidores por cable. Por eso se elige el Latitude 3550, que lo incluye de serie.
3. **Servidores separados con RAID.** Se mantiene un servidor por servicio, como dice el documento de recursos. Los modelos T160 sirven para los servicios más ligeros (Dominio, Correo, Web). El T360 se usa donde hace falta más capacidad o una controladora RAID avanzada (Ficheros con RAID 5 y Base de datos con RAID 10).
4. **Base de datos como servidor más caro.** Es el servidor más importante (clientes, citas y facturas), así que se pone un T360 de 32 GB con garantía de 3 años y discos SSD en RAID 10.
5. **Red.** Ubiquiti UniFi es una solución profesional con buen precio y gestión centralizada. El firewall FortiGate incluye las protecciones de seguridad (IPS, antivirus, filtrado web), que casan con el requisito de seguridad de la empresa.
6. **SAI de 3000 VA.** Es el elemento más caro de la red, pero mantiene encendidos los servidores si se va la luz, y la pérdida de datos costaría más.
7. **Licencias.**
   - Windows Server necesita una licencia por servidor físico y una CAL por usuario.
   - Microsoft 365 se contrata por suscripción anual (opción de Microsoft para empresas).
   - Odoo cubre clientes, citas y facturas con 6 usuarios.
   - ESET protege los 27 equipos y los 5 servidores con una sola consola.
   - Ubuntu Server y las herramientas de redes y desarrollo son gratuitas, lo que ahorra dinero.
8. **Razonabilidad económica.** La inversión inicial ronda los 60.600 € con IVA (≈ 1.950 € por puesto de trabajo, contando 31 personas entre trabajadores y equipo de implantación). Es una cifra proporcionada para una empresa del sector TIC con un volumen de negocio de unos 50 millones al año. El coste recurrente (≈ 9.200 €/año) es asumible.

### Lo que NO incluye este presupuesto

- **Monitores, teclados, ratones y periféricos** de los sobremesas (no aparecen en el documento de recursos).
- **Cableado estructurado, rack, cables DAC/SFP+ de 10 Gb y tomas de red** (aparecen como tarea del técnico de cableado, pero no como recurso material).
- **Coste del equipo de implantación** (6 personas): es personal propio de la empresa, su coste ya está en nómina.
- **Transporte e instalación.**

Si el profesorado lo pide, conviene añadir estos materiales también al documento de recursos para mantener la coherencia.

---

## Fuentes (consultables)

| Nº | Producto | Enlace |
|:---:|---|---|
| [1] | Dell Pro 14 PC14250 (878,16 € con IVA) | https://www.pccomponentes.com/portatiles/14-pulgadas/dell/primera-generacion |
| [2] | Dell Latitude 3550 (839 € con IVA) | https://www.pccomponentes.com/portatiles/16gb-ram/dell/intel-core-ultra-5/windows |
| [3] | PcCom Work i5-12400 16 GB (539 € con IVA) | https://www.pccomponentes.com/sobremesa/16gb-ram/64gb-ram/windows/windows-11-pro |
| [4] | PcCom Work i7-12700 32 GB (789 € con IVA) y ThinkStation P2 (1.999 € con IVA) | https://www.pccomponentes.com/sobremesa/1-tb-ssd/32-gb-ram/intel-i7/windows-11-pro |
| [5] | Dell PowerEdge T160 (1.109 € con IVA) y T360 E-2414 (1.838,99 € con IVA) | https://www.pccomponentes.com/ordenadores-sobremesa/dell |
| [6] | Seagate IronWolf 2 TB (147,77 € con IVA) y IronWolf Pro 4 TB (199,95 € con IVA) | https://www.pccomponentes.com/discos-duros/internos/seagate · https://www.pccomponentes.com/discos-duros/hdd-mecanico/internos/seagate |
| [7] | Dell PowerEdge T160 Xeon 6325P 32 GB (1.731,07 € con IVA) | https://www.pccomponentes.com/servidores/sin-s-o/sin-sistema-operativo |
| [8] | Kingston DC600M 480 GB (desde 161,99 € sin IVA) | https://www.bechtle.com/es/finder/product-family/ssd-internas-kingston-dc600m--4851--f |
| [9] | Dell PowerEdge T360, 32 GB (3.968,00 € sin IVA) | https://www.bechtle.com/es/shop/servidores-dell-poweredge-t360--4993540--p |
| [10] | MikroTik RB5009UG+S+IN (214 € con IVA) | https://comprasmartphone.com/routers/mikrotik-rb5009ug-plus-s-plus-in-router |
| [11] | FortiGate 70F + UTP 1 año (1.461,00 € sin IVA) | https://www.bechtle.com/it-en/shop/fortinet-fortigate-70f-hardware-plus-forticare-premium-and-fortiguard-unified-threat-protection-utp-for-1-year--4691542--p |
| [12] | Ubiquiti USW-Pro-Aggregation (1.078,40 € con IVA de Estonia, 24 %) | https://arvutitark.ee/ru/network-devices/switches/ubiquiti-switch-aggregation-1026787 |
| [13] | Ubiquiti USW-Pro-24-POE (623,70 € neto) | https://www.esus-it.de/product-ger-55994-Switch-Ubiquiti-USW-PRO-24-POE-24x-10-100-1000-2x-SFP-400-W-PoE-PoE.html |
| [14] | Ubiquiti U6 Pro (188,15 € con IVA) | https://www.pccomponentes.com/ubiquiti-networks-u6-pro-punto-de-acceso-inalambrico-wifi-6-4800-mbit-s-poe-blanco |
| [15] | APC Smart-UPS SMT3000RMI2UC (2.701,40 € sin IVA) | https://opencircuit.shop/product/apc-smart-ups-smt3000rmi2uc-3000-va-2700-w |
| [16] | Windows Server 2025 Standard 16 núcleos OEM (949,00 € neto) | https://software-express.de/preislisten/microsoft/microsoft-500040 |
| [17] | Windows Server 2025 CAL de usuario perpetua (54,00 €; la web no indica IVA, se trata como sin IVA) | https://shop.aodatacloud.es/microsoft-windows-server |
| [18] | Ubuntu Server (gratuito) | https://ubuntu.com/server |
| [19] | Microsoft 365 Empresa Estándar, 20,36 €/usuario/mes sin IVA | https://www.microsoft.com/es-es/microsoft-365/business/microsoft-365-plans-and-pricing |
| [20] | Odoo Standard, 14,90 €/usuario/mes con pago anual (precio en España según una guía externa; comprobar en la web oficial) | https://www.guiadesoftware.com/blog/cuanto-cuesta-odoo · https://www.odoo.com/es_ES/pricing |
| [21] | ESET PROTECT Entry 26-49, 1 año (23,99 € sin IVA) | https://bechtle.com/de-en/shop/eset-protect-entry-26-49-1y--108534721--p |
| [22] | Veeam Data Platform Foundation, pack de 10 instancias 1 año = 1.550 USD. Se calcula 155 USD por instancia y se convierte con un cambio **aproximado** de 0,86 €/USD (comprobar el cambio real) | https://www.shi.com/product/46221767/Veeam-Data-Platform-Foundation-Universal-License |
| [23] | Packet Tracer, Wireshark, VirtualBox, VS Code y Git (gratuitos) | https://www.netacad.com · https://www.wireshark.org · https://www.virtualbox.org · https://code.visualstudio.com · https://git-scm.com |
| [24] | Renovación UTP FortiGate 70F, 1 año (603,75 € sin IVA) | https://www.kommago.nl/p/unified-threat-protection-fortigate-70f-1-yr-79928 |

> **Nota sobre el firewall:** Fortinet ha anunciado el fin de pedidos del modelo 70F (mayo de 2026) y su sustituto es el FortiGate 70G. El precio del 70F se usa como referencia de gama; en una compra real habría que presupuestar el 70G.