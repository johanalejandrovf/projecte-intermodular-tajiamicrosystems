# Alternativas y estudio de viabilidad

Para las necesidades más importantes del documento `01-necessitats.md` hemos estudiado dos alternativas antes de decidir. En cada una comparamos ventajas, limitaciones, coste aproximado y requisitos técnicos.

## Alternativa 1: servidores propios o servicios en la nube

### Comparación

| Criterio | Servidores propios | Servicios en la nube |
|----------|--------------------|----------------------|
| Inversión inicial | Alta: hay que comprar los equipos | Ninguna |
| Coste mensual | Bajo: solo luz y mantenimiento | Alto: cuota fija todos los meses |
| Control de los datos | Total: están en la empresa | Están en servidores de otra empresa |
| Velocidad en la oficina | Muy alta, es red local | Depende de la conexión a Internet |
| Si se cae Internet | Se sigue trabajando dentro | No se puede trabajar |
| Mantenimiento | Lo hacemos nosotros | Lo hace el proveedor |
| Crecer o reducir | Hay que comprar más equipos | Se cambia la cuota y ya está |

### Coste aproximado a 5 años

| Concepto | Servidores propios | Servicios en la nube |
|----------|--------------------|----------------------|
| Compra de equipos | 14.000 € | 0 € |
| Puesta en marcha | Incluida en la implantación | 1.000 € |
| Gasto anual | 2.000 € | 5.400 € |
| **Total a 5 años** | **24.000 €** | **28.000 €** |

### Requisitos técnicos

| | Servidores propios | Servicios en la nube |
|---|---|---|
| Espacio | Sala de servidores con rack y ventilación | No hace falta |
| Conexión | Red local propia | Fibra rápida y estable, obligatoria |
| Personal | Alguien que sepa administrar servidores | Menos personal técnico |
| Protección eléctrica | SAI | No hace falta |

### Opción elegida: servidores propios

La elegimos por tres motivos:

- **Es más barata a medio plazo.** A partir del cuarto año sale mejor la opción propia, y los equipos siguen sirviendo después.
- **Controlamos los datos.** Trabajamos con datos de clientes, y tenerlos en la empresa nos facilita cumplir con la protección de datos.
- **No dependemos de Internet para trabajar.** Si se cae la fibra, los trabajadores siguen accediendo a los ficheros, al dominio y a la base de datos.

La limitación es que necesitamos la inversión inicial y alguien que mantenga los servidores. Lo asumimos porque el departamento de Taller ya tiene administradores de sistemas.

## Alternativa 2: red toda cableada o red mixta

### Comparación

| Criterio | Toda cableada | Mixta (cable + Wi-Fi) |
|----------|---------------|------------------------|
| Velocidad | Máxima en todos los equipos | Máxima por cable, algo menor por Wi-Fi |
| Estabilidad | Muy alta | Alta, puede haber interferencias |
| Movilidad | Ninguna | Los portátiles se mueven libremente |
| Seguridad | Muy alta, hay que enchufarse | Alta, con WPA3 y red de invitados aparte |
| Obra necesaria | Una toma por cada equipo | Solo en los puestos fijos |
| Visitantes | No tienen conexión | Red de invitados separada |

### Coste aproximado

| Concepto | Toda cableada | Mixta |
|----------|---------------|-------|
| Tomas de red (70 € cada una) | 35 tomas: 2.450 € | 20 tomas: 1.400 € |
| Puntos de acceso Wi-Fi | 0 € | 2 puntos: 500 € |
| **Total** | **2.450 €** | **1.900 €** |

### Requisitos técnicos

| | Toda cableada | Mixta |
|---|---|---|
| Cableado | Cable hasta cada puesto | Solo hasta los puestos fijos |
| Switches | Más puertos | 2 switches de 24 puertos |
| Equipos extra | Ninguno | 2 puntos de acceso Wi-Fi 6 |

### Opción elegida: red mixta

- **Cable** para los ordenadores de sobremesa, las impresoras y los servidores, que no se mueven y necesitan la máxima velocidad.
- **Wi-Fi** para los portátiles de Dirección e Implantación, que entran y salen continuamente.
- Además, nos permite tener una **red de invitados separada**, que con cable no tendría sentido.

Sale más barata que cablearlo todo y da movilidad. La limitación es que el Wi-Fi es algo más lento, pero los portátiles no hacen tareas que necesiten la máxima velocidad.

## Aspecto innovador: copia de seguridad híbrida

### En qué consiste

Las copias de seguridad no se guardan solo en el servidor de ficheros. Cada noche, una **copia cifrada** se envía automáticamente a un almacenamiento en la nube.

Es lo que se conoce como la **regla 3-2-1**: tres copias de los datos, en dos sitios distintos y una de ellas fuera de la empresa.

### Para qué sirve

| Situación | Sin copia en la nube | Con copia en la nube |
|-----------|----------------------|----------------------|
| Falla un disco | Se recupera del servidor | Se recupera del servidor |
| Incendio o robo | Se pierde todo | Se recupera la copia de fuera |
| Ransomware | Puede cifrar también las copias | La copia de fuera queda a salvo |

### Coste y requisitos

| Concepto | Valor |
|----------|-------|
| Coste | Unos 120 € al año por 2 TB |
| Requisitos | Conexión de fibra y software de copias (Veeam) |
| Quién lo lleva | El técnico de seguridad del Taller |

**Utilidad:** por muy poco dinero cubrimos el único riesgo que las copias locales no cubren, que es perder el edificio entero o un ataque que cifre también el servidor de copias. Para una empresa que guarda datos de clientes, es la mejora que más aporta por lo que cuesta.

## Estudio de viabilidad

### Espacios

| Necesidad | ¿Lo cumplimos? |
|-----------|----------------|
| Sala de servidores con rack y ventilación | Sí, un rack de 42U es suficiente para 5 servidores y los equipos de red |
| Distancia de los cables | Sí, ningún cable pasa de 100 metros, que es el límite del cable de red |
| Zonas de la oficina | Sí, con 2 switches de acceso cubrimos las dos zonas de trabajo |
| Cobertura Wi-Fi | Sí, 2 puntos de acceso bastan para una oficina de 25 personas |

### Conocimientos disponibles

| Necesidad | ¿Lo cumplimos? |
|-----------|----------------|
| Administrar Windows Server y Ubuntu | Sí, el Taller tiene 2 administradores de sistemas |
| Configurar VLAN, firewall y VPN | Sí, es el trabajo habitual de Implantación |
| Seguridad y copias | Sí, el Taller tiene un técnico de seguridad |
| Formar a los usuarios | Sí, lo hace el técnico de soporte durante la implantación |

No hace falta ninguna tecnología que el equipo no conozca ya.

### Equipos

| Necesidad | Previsto en `05-recursos.md` |
|-----------|------------------------------|
| Un ordenador por trabajador | 27 ordenadores para 25 trabajadores (2 de pruebas) |
| Servidores para los servicios | 5 servidores |
| Equipos de red | 1 router, 1 firewall, 3 switches, 2 puntos de acceso |
| Protección eléctrica | 1 SAI |

Todo lo que necesita el diseño está en la lista de recursos: no falta ningún equipo ni sobra ninguno.

### Presupuesto

| Concepto | Coste aproximado |
|----------|------------------|
| Ordenadores (27) | 30.000 € |
| Servidores (5) | 12.500 € |
| Equipos de red y cableado | 8.000 € |
| Licencias (primer año) | 10.000 € |
| Mano de obra de la implantación | 8.000 € |
| **Total aproximado** | **68.500 €** |

Es una inversión que se reparte en unos 5 años, que es lo que duran los equipos, o sea unos **13.700 € al año**. El detalle está en el documento `06-pressupost.md`.

### Conclusión

La solución es viable: cabe en el espacio disponible, el equipo sabe montarla y mantenerla, los equipos previstos cubren todas las necesidades y el presupuesto es asumible para una empresa de este tamaño.