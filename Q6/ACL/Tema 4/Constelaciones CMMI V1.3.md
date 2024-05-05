[[Tema 4-CMMI]]
$\space$
## 1.Qué es CMMI?
CMMI son las siglas de Capability Maturity Model Integration. Fue desarrollado para el Software Engineering Institute (SEI).

Es una guía que sirve para mejorar los procesos asociados al desarrollo y mantenimiento de software. A diferencia de ISO está solo enfocado al software y los resultados de las auditorías que realizan son públicos.
$\space$
## 2.Qué es una constelación CMMI?
Una constelación CMMI es un conjunto de prácticas y procesos que se agrupan para formar un modelo que se puede utilizar en un área específica de interés dentro de una organización.
$\space$
### 2.1.Constelaciones CMMI V1.3
La versión 1.3 de CMMI separa el modelo en 3 constelaciones:
+ **CMMI-DEV (development)**: guía para desarrollo de productos y servicios software.
+ **CMMI-ACQ(acquisition):** compra de productos y servicios.
+ **CMMI-SVC(services):** gestión de servicios a clientes.
$\space$
## 3.Niveles de madurez
A diferencia de ISO, CMMI mide la calidad en niveles de madurez. En la ISO una empresa o está certificada o no. En cambio, CMMI propone varios niveles donde en cada uno hay un conjunto de objetivos a alcanzar llamados Process Areas (PA). Una vez alcanzados todos esos objetivos se pasa de nivel.

No es posible saltarse niveles. Se puede solicitar directamente auditar para nivel 3, por ejemplo, pero una vez esté la organización en nivel 3 tiene que auditarse de nivel 4 antes de pasar al 5.

![[niveles CMMI.png]]
$\space$
## 4.Process Areas
Una PA es un conjunto de prácticas relacionadas que el implementarlas correctamente satisfacen un conjunto de metas que afectan directamente a la calidad de la zona en la que se enfocan.
$\space$
### 4.1.Metas
Las metas pueden ser:
+ **Genéricas (GG):** son objetivos en múltiples PAs.
+ **Específicas (SG):** son objetivos que solo aplican a una PA.
$\space$
### 4.2.Prácticas
Las prácticas son subdivisiones de las metas. No son obligatorias, se usan como ejemplo de posibles prácticas que se pueden hacer para satisfacer las metas. Si la organización es capaz de demostrar que su proposición es igual de válida que las prácticas que propone CMMI, es totalmente válido utilizarla. 

Las prácticas propuestas también se dividen en:
+ **Genéricas (GP):** se aplican a múltiples PA para satisfacer las GG. 
+ **Específicas (SP):** se aplican a una PA para satisfacer una SG.
$\space$
### 4.3.Esquema CMMI

![[PA de CMMI.png]]

Las metas se subdividen en prácticas y estas a su vez en tareas más pequeñas denominadas subprácticas, que generan una salida. Cada práctica genérica tiene elaboraciones que proporcionan pautas detalladas y específicas para su implementación en contextos particulares. Estas elaboraciones son guías particulares que se adaptan a las necesidades y requisitos específicos de cada área de proceso a la que afectan.
$\space$
### 4.4.Lista de PAs
CMMI propone 16 PA base y, además, otras PA específicas para cada constelación.
$\space$
#### 4.4.1.PAs base
Las PA básicas son aquellas que son genéricas a todas las áreas de una organización:
+ **PP:** Planificación de Proyectos (Gestión de Proyectos, N2)
+ **PCM:** Monitorización y control de Proyectos (Gestión de Proyectos, N2)
+ **IPM:** Gestión Integrada del Proyecto (Gestión de Proyectos, N3)
+ **RSKM:** Gestión de Riesgos (Gestión de Proyectos, N3)
+ **QPM:** Gestión Cuantitativa del Proyecto (Gestión de Proyectos, N4)
+ **REQM:** Gestión de Requisitos (Gestión de Proyectos, N2)
+ **OPD:** Definición de Procesos de la Organización (Gestión de Procesos, N3)
+ **OPF:** Enfoque de Procesos de la Organización (Gestión de Procesos, N3)
+ **OT:** Formación de la Organización (Gestión de Procesos, N3)
+ **OPP:** Rendimiento de Procesos de la Organización (Gestión de Procesos, N4)
+ **OPM:** Gestión del Rendimiento de la Organización (Gestión de Procesos, N5)
+ **MA:** Medición y Análisis (Soporte, N2)
+ **PPQA:** Aseguramiento de la Calidad del Proceso y del Producto (Soporte, N2)
+ **CM:** Gestión de la Configuración (Soporte, N2)
+ **DAR:** Análisis de Decisiones y Resolución (Soporte, N3)
+ **CAR:** Análisis Causal y Resolución (Soporte, N3)
$\space$
#### 4.4.2.PA de CMMI-SVC
Las PA aplicadas a servicios son:
+ **CAM:** Gestión de la Capacidad y Disponibilidad
+ **IRP:** Prevención y Resolución de Incidencias 
+ **SAM:** Gestión de Acuerdos con Proveedores
+ **SCON:** Continuidad del Servicio
+ **SD:** Entrega del Servicio
+ **SSD:** Desarrollo de Servicios
+ **SST:** Transmisión de Servicios
+ **STSM:** Gestión Estratégica de Servicio
$\space$
#### 4.4.3.PA de CMMI-ACQ
Las PA aplicadas a la adquisición son:
+ **ARD:** Desarrollo de Requisitos de Adquisición
+ **AM:** Gestión de Acuerdos
+ **ATM:** Gestión de la Adquisición Técnica
+ **AVAL:** Validación de la Adquisición
+ **AVER:** Verificación de la Adquisición
+ **SSAD:** Desarrollo de la Solicitud y Acuerdo de Adquisición 
$\space$
#### 4.4.4.PA de CMMI-DEV
Las PA aplicadas al desarrollo son:
+ **PI:** Integración del Producto (Ingeniería, N3)
+ **RD:** Desarrollo de Requisitos (Ingeniería, N3)
+ **SAM:** Gestión de Acuerdos con Proveedores (Gestión de Proyectos, N2)
+ **TS:** Solución Técnica (Ingeniería, N3)
+ **VAL:** Validación (Ingeniería, N3)
+ **VER:** Verificación (Ingeniería, N3)
$\space$
#### 4.4.5.Organización en niveles

![[escalones CMMI.png]]


