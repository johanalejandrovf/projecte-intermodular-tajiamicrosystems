# Plan de direccionamiento IP y nombres de los equipos

## Redes definidas

| Red | Dirección | Máscara | Prefijo | Puerta de enlace | Uso |
|-----|-----------|---------|---------|------------------|-----|
| Externa (WAN) | 10.0.2.0 | 255.255.255.0 | /24 | 10.0.2.2 | Salida a Internet |
| Red interna (LAN) | 192.168.1.0 | 255.255.255.0 | /24 | 192.168.1.1 | Equipos y servidores internos |
| DMZ | 172.16.0.0 | 255.255.255.0 | /24 | 172.16.0.1 | Servicios públicos |

Las tres son redes privadas y **no se solapan entre sí**: pertenecen a rangos distintos (10.0.0.0/8, 172.16.0.0/12 y 192.168.0.0/16).

Cada red /24 admite **254 direcciones útiles**, de la .1 a la .254. La .0 es la dirección de red y la .255 la de difusión, y no se asignan a ningún equipo.

## Cómo hemos repartido la red interna

Aunque todos los equipos están en la misma red, hemos reservado **un rango de diez direcciones a cada departamento**. Así, viendo la IP de un equipo ya se sabe de dónde es:

| Rango | Para | Direcciones en uso |
|-------|------|--------------------|
| 192.168.1.1 | Firewall (puerta de enlace) | 1 |
| 192.168.1.10 – .19 | Servidores internos | 2 |
| 192.168.1.20 – .29 | Dirección | 2 |
| 192.168.1.30 – .39 | Gestión (equipos .30–.38, impresora .39) | 5 |
| 192.168.1.40 – .49 | Taller (equipos .40–.48, impresora .49) | 7 |
| 192.168.1.50 – .59 | Desarrollo web | 4 |
| 192.168.1.60 – .69 | Implantación | 8 |
| 192.168.1.70 – .254 | Libres, para crecer | 0 |

Las impresoras ocupan siempre **la última dirección del rango de su departamento** (.39 y .49), para no mezclarlas con los equipos de los trabajadores.

## Tabla de direccionamiento

### Equipos de red y servidores

| Nombre del equipo | Red | Dirección IP | Máscara | Puerta de enlace |
|-------------------|-----|--------------|---------|------------------|
| TAJIA-FW (WAN) | Externa | 10.0.2.15 | 255.255.255.0 | 10.0.2.2 |
| TAJIA-FW (LAN) | Interna | 192.168.1.1 | 255.255.255.0 | — |
| TAJIA-FW (DMZ) | DMZ | 172.16.0.1 | 255.255.255.0 | — |
| TAJIA-SRV-DOM | Interna | 192.168.1.10 | 255.255.255.0 | 192.168.1.1 |
| TAJIA-NAS-BK | Interna | 192.168.1.11 | 255.255.255.0 | 192.168.1.1 |
| TAJIA-SRV-WEB | DMZ | 172.16.0.10 | 255.255.255.0 | 172.16.0.1 |
| TAJIA-SRV-MAIL | DMZ | 172.16.0.11 | 255.255.255.0 | 172.16.0.1 |

La dirección WAN del firewall (10.0.2.15) la recibe por DHCP del router. Todas las demás son fijas.

### Equipos cliente e impresoras

| Nombre del equipo | Departamento | Dirección IP | Puerto del switch |
|-------------------|--------------|--------------|-------------------|
| TAJIA-DIR-01 | Dirección | 192.168.1.20 | 4 |
| TAJIA-DIR-02 | Dirección | 192.168.1.21 | 5 |
| TAJIA-GES-01 | Gestión | 192.168.1.30 | 6 |
| TAJIA-GES-02 | Gestión | 192.168.1.31 | 7 |
| TAJIA-GES-03 | Gestión | 192.168.1.32 | 8 |
| TAJIA-GES-04 | Gestión | 192.168.1.33 | 9 |
| TAJIA-IMP-GES | Gestión (impresora) | 192.168.1.39 | 10 |
| TAJIA-TAL-01 | Taller | 192.168.1.40 | 11 |
| TAJIA-TAL-02 | Taller | 192.168.1.41 | 12 |
| TAJIA-TAL-03 | Taller | 192.168.1.42 | 13 |
| TAJIA-TAL-04 | Taller | 192.168.1.43 | 14 |
| TAJIA-TAL-05 | Taller | 192.168.1.44 | 15 |
| TAJIA-TAL-06 | Taller | 192.168.1.45 | 16 |
| TAJIA-IMP-TAL | Taller (impresora) | 192.168.1.49 | 17 |
| TAJIA-WEB-01 | Desarrollo web | 192.168.1.50 | 18 |
| TAJIA-WEB-02 | Desarrollo web | 192.168.1.51 | 19 |
| TAJIA-WEB-03 | Desarrollo web | 192.168.1.52 | 20 |
| TAJIA-WEB-04 | Desarrollo web | 192.168.1.53 | 21 |
| TAJIA-IMPL-01 | Implantación | 192.168.1.60 | 22 |
| TAJIA-IMPL-02 | Implantación | 192.168.1.61 | 23 |
| TAJIA-IMPL-03 | Implantación | 192.168.1.62 | 24 |
| TAJIA-IMPL-04 | Implantación | 192.168.1.63 | 25 |
| TAJIA-IMPL-05 | Implantación | 192.168.1.64 | 26 |
| TAJIA-IMPL-06 | Implantación | 192.168.1.65 | 27 |
| TAJIA-IMPL-07 | Implantación | 192.168.1.66 | 28 |
| TAJIA-IMPL-08 | Implantación | 192.168.1.67 | 29 |

Todos los equipos cliente usan **máscara 255.255.255.0** y **puerta de enlace 192.168.1.1**.

## Convención de nombres

Los nombres siguen siempre el mismo patrón:

```
TAJIA - <DEPARTAMENTO o FUNCIÓN> - <NÚMERO>
```

| Parte | Significado | Ejemplos |
|-------|-------------|----------|
| TAJIA | Nombre de la empresa | — |
| Departamento | DIR, GES, TAL, WEB, IMPL | TAJIA-GES-02 |
| Función | SRV (servidor), NAS, FW (firewall), IMP (impresora) | TAJIA-SRV-WEB |
| Número | Dos cifras, correlativo dentro del departamento | TAJIA-TAL-05 |

Con solo leer el nombre se sabe de qué departamento es el equipo y qué función tiene. Los nombres cumplen las reglas de NetBIOS: menos de 15 caracteres, sin acentos ni espacios.

## Configuración que recibe cada equipo

| Parámetro | Equipos de la red interna | Servidores de la DMZ |
|-----------|---------------------------|----------------------|
| Dirección IP | Fija, según la tabla | Fija, según la tabla |
| Máscara | 255.255.255.0 | 255.255.255.0 |
| Puerta de enlace | 192.168.1.1 (firewall) | 172.16.0.1 (firewall) |
| DNS | 192.168.1.10 (servidor de dominio) | 8.8.8.8 |

El servidor de dominio resuelve los nombres internos de la empresa y **reenvía a 8.8.8.8** las consultas de Internet. Los servidores de la DMZ apuntan directamente a 8.8.8.8 para que no dependan de la red interna.

## Justificación de la separación entre red interna y DMZ

- **Son dos redes distintas y con numeración distinta.** La interna es 192.168.1.0/24 y la DMZ es 172.16.0.0/24. Un equipo de una red no puede hablar con el otro sin pasar por el firewall.
- **Cada zona está en un puerto físico distinto del firewall.** No comparten switch ni cableado, así que la separación es física y no solo lógica.
- **El firewall decide qué pasa entre ellas.** Desde Internet solo se llega a la DMZ, y solo a los puertos de web y correo. Desde la DMZ no se puede iniciar ninguna conexión hacia la red interna.
- **Los servidores públicos son los más expuestos.** Si alguien compromete la web o el correo, no obtiene ningún acceso al dominio, a las carpetas compartidas ni a las copias de seguridad.
- **Simplifica las reglas del firewall.** Al estar cada zona en su propio rango, las reglas se escriben por red completa y no equipo por equipo, lo que reduce las posibilidades de equivocarse.

## Comprobación del plan

| Comprobación | Resultado |
|--------------|-----------|
| ¿Se solapan las redes? | No. 10.0.2.0/24, 192.168.1.0/24 y 172.16.0.0/24 son rangos distintos |
| ¿Hay direcciones repetidas? | No. Cada equipo tiene una dirección única dentro de su red |
| ¿Se usan la .0 o la .255? | No. Están reservadas para red y difusión |
| ¿Caben todos los equipos? | Sí. 29 direcciones usadas de 254 disponibles en la LAN (11 %) |
| ¿Hay sitio para crecer? | Sí. Quedan libres 225 direcciones y 3 puertos del switch |
| ¿Coincide con el diagrama? | Sí. Mismas direcciones y mismos puertos que en `03-disseny-xarxa.md` |

**Recuento de direcciones usadas en la red interna:** 1 firewall + 2 servidores + 2 Dirección + 4 Gestión + 1 impresora + 6 Taller + 1 impresora + 4 Desarrollo web + 8 Implantación = **29 direcciones**.