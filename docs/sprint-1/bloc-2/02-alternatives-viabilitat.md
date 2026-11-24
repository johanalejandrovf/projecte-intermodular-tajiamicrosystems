# Alternativas y estudio de viabilidad

Para las necesidades más importantes del documento `01-necessitats.md` hemos estudiado dos alternativas antes de decidir. En cada una comparamos ventajas, limitaciones, coste aproximado y requisitos técnicos.

## Alternativa 1: servidores propios o servicios alojados en la nube

### Comparación

| Criterio | Servidores propios | Servicios en la nube |
|----------|--------------------|----------------------|
| Inversión inicial | Alta: hay que comprar los equipos | Ninguna |
| Coste mensual | Bajo: luz y mantenimiento | Alto: cuota fija todos los meses |
| Control de los datos | Total: están en la empresa | Están en servidores de otra empresa |
| Velocidad en la oficina | Muy alta, es red local | Depende de la conexión a Internet |
| Si se cae Internet | Se sigue trabajando dentro | No se puede trabajar |
| Mantenimiento | Lo hacemos nosotros | Lo hace el proveedor |
| Crecer o reducir | Hay que comprar más equipos | Se cambia la cuota y ya está |

### Coste aproximado a 5 años

| Concepto | Servidores propios | Servicios en la nube |
|----------|--------------------|----------------------|
| Compra de equipos | 2.600 € | 0 € |
| Puesta en marcha | Incluida en la implantación | 1.000 € |
| Gasto anual | 600 € | 4.800 € |
| **Total a 5 años** | **5.600 €** | **25.000 €** |

### Requisitos técnicos

| | Servidores propios | Servicios en la nube |
|---|---|---|
| Espacio | Armario rack en la sala de servidores | No hace falta |
| Conexión | Red local propia | Fibra rápida y estable, obligatoria |
| Personal | Alguien que sepa administrar servidores | Menos personal técnico |
| Protección eléctrica | SAI | No hace falta |

### Opción elegida: servidores propios

La elegimos por tres motivos:

- **Es mucho más barata.** A partir del primer año ya sale mejor, y los equipos siguen sirviendo después.
- **Controlamos los datos.** Trabajamos con datos de clientes, y tenerlos en la empresa nos facilita cumplir con la protección de datos.
- **No dependemos de Internet para trabajar.** Si se cae la fibra, los trabajadores siguen accediendo al dominio, a las carpetas compartidas y a las copias.

La limitación es que necesitamos la inversión inicial y alguien que mantenga los servidores. La asumimos porque el departamento de Taller ya tiene administradores de sistemas.

## Alternativa 2: una sola red interna o varias redes separadas por departamento

### Comparación

| Criterio | Una sola red (elegida) | Una red por departamento |
|----------|------------------------|--------------------------|
| Equipos de red | 1 switch de 32 puertos | 5 switches + enrutamiento entre redes |
| Configuración | Sencilla: todos en 192.168.1.0/24 | Compleja: rutas y permisos entre redes |
| Comunicación entre departamentos | Directa, por el switch | Tiene que pasar por el router o firewall |
| Separación de tráfico | Todos comparten el mismo dominio de difusión | Cada departamento aislado |
| Mantenimiento | Lo lleva una persona sin problema | Necesita más conocimientos |
| Coste | Más bajo | Más alto |

### Coste aproximado

| Concepto | Una sola red | Una red por departamento |
|----------|--------------|--------------------------|
| Switch de 32 puertos | 1.113 € | — |
| Switches de 8 y 16 puertos | — | 5 switches: unos 900 € |
| Equipo que enrute entre redes | Lo hace el firewall | Switch de nivel 3: unos 800 € |
| **Total** | **1.113 €** | **1.700 €** |

### Requisitos técnicos

| | Una sola red | Una red por departamento |
|---|---|---|
| Direccionamiento | Un único rango /24 | Cinco rangos distintos |
| Equipos | 1 switch gestionable | 5 switches + enrutamiento |
| Conocimientos | Básicos | Enrutamiento y reglas entre redes |

### Opción elegida: una sola red interna

Con 24 trabajadores no compensa dividir la empresa en varias redes. Una sola red de 254 direcciones sobra para los 29 equipos actuales y deja sitio para crecer, es más barata y mucho más fácil de mantener.

Para no perder el orden, **reservamos un rango de direcciones a cada departamento** (ver `04-adrecament-ip.md`): viendo la IP de un equipo ya se sabe de qué departamento es, aunque todos estén en la misma red.

La limitación es que todos los equipos comparten el mismo dominio de difusión y no hay aislamiento entre departamentos. Lo asumimos porque la separación que de verdad importa, la de los servicios públicos, sí la tenemos: está en la DMZ.

## Aspecto innovador: copia de seguridad híbrida (local y en la nube)

### En qué consiste

Las copias de seguridad no se guardan solo en el NAS de la oficina. Cada noche, una **copia cifrada** se envía automáticamente a un almacenamiento en la nube.

Es lo que se conoce como la **regla 3-2-1**: tres copias de los datos, en dos soportes distintos y una de ellas fuera de la empresa.

### Para qué sirve

| Situación | Solo con copias locales | Con copia también en la nube |
|-----------|-------------------------|------------------------------|
| Falla un disco | Se recupera del NAS (RAID) | Se recupera del NAS |
| Incendio, inundación o robo | Se pierde todo | Se recupera la copia de fuera |
| Ransomware que cifra la red | Puede cifrar también el NAS | La copia de fuera queda a salvo |

### Coste y requisitos

| Concepto | Valor |
|----------|-------|
| Coste aproximado | Unos 120 € al año por 2 TB |
| Requisitos | Conexión de fibra y el software Hyper Backup, que ya incluye el NAS |
| Quién lo lleva | El administrador de sistemas del Taller |

**Valoración de la utilidad:** por muy poco dinero cubrimos el único riesgo que las copias locales no cubren, que es perder el edificio entero o sufrir un ataque que cifre también el servidor de copias. Para una empresa que guarda datos de clientes, es la mejora que más aporta por lo que cuesta. Además, el NAS elegido trae el software incluido, así que no hay que comprar nada más.

## Estudio de viabilidad

### Coherencia con los espacios

| Necesidad | ¿Lo cumplimos? |
|-----------|----------------|
| Sala de servidores | Sí, un armario rack de 12U es suficiente para el firewall, el switch, el NAS y el SAI |
| Distancia del cableado | Sí, ningún cable pasa de 100 metros, que es el límite del cable de par trenzado |
| Tomas de red | Sí, 29 tomas para los equipos actuales y 3 puertos libres en el switch |
| Ventilación y electricidad | Sí, la sala de servidores tiene toma de corriente propia y el SAI protege los equipos críticos |

### Coherencia con los conocimientos disponibles

| Necesidad | ¿Lo cumplimos? |
|-----------|----------------|
| Administrar Windows Server (dominio, DNS) | Sí, el Taller tiene administradores de sistemas |
| Administrar Ubuntu Server (web y correo) | Sí, es el trabajo habitual del Taller y de Desarrollo web |
| Configurar firewall, NAT y DMZ | Sí, es el trabajo habitual del departamento de Implantación |
| Configurar el switch y el cableado | Sí, Implantación lo hace a diario en casa de los clientes |
| Formar a los usuarios | Sí, lo hace el técnico de soporte durante la implantación |

No hace falta ninguna tecnología que el equipo no conozca ya. Tampoco hace falta contratar personal nuevo de forma permanente.

### Coherencia con los equipos previstos

| Necesidad | Previsto en `05-recursos.md` |
|-----------|------------------------------|
| Un ordenador por trabajador | 24 ordenadores para 24 trabajadores |
| Servidor de dominio | 1 servidor |
| Copias de seguridad | 1 NAS con 4 discos en RAID |
| Servicios públicos | 2 servidores en la DMZ: web y correo |
| Conectar todos los equipos | 1 switch de 32 puertos (29 usados, 3 libres) |
| Proteger la red | 1 firewall con puerto LAN y puerto DMZ |
| Impresión | 2 impresoras multifunción en red |
| Protección eléctrica | 1 SAI |

Todo lo que necesita el diseño está en la lista de recursos: no falta ningún equipo ni sobra ninguno.

### Coherencia con el presupuesto previsto

| Concepto | Importe aproximado |
|----------|--------------------|
| Equipos (hardware) | 22.300 € |
| Licencias de compra | 3.770 € |
| Suscripciones del primer año | 3.140 € |
| Cableado e implantación | 5.000 € |
| **Total aproximado** | **34.200 €** |

Es una inversión que se reparte en unos 5 años, que es lo que duran los equipos, o sea unos **6.840 € al año**. Para una empresa de 24 trabajadores del sector informático es una cifra asumible. El detalle, con precios reales y enlaces, está en `06-pressupost.md`.

### Conclusión

La solución es viable: cabe en el espacio disponible, el equipo sabe montarla y mantenerla, los equipos previstos cubren todas las necesidades identificadas y el presupuesto es razonable para una empresa de este tamaño.