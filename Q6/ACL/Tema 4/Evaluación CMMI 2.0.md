[[Tema 4-CMMI]]
$\space$
## 1.Auditorías
Cuando las empresas consiguen mejorar sus procesos se someten a auditorías que corroboren que se ha implementado CMMI correctamente mediante un auditor externo. No se entrega certificación oficial, simplemente se entregan unos diplomas conforme se ha pasado la prueba.
$\space$
### 1.1.Tipos de auditorías
Hay tres tipos de auditorías:
+ **Benchmark appraisal:** son las auditorías más rigurosas. Se entrega el diploma que acredita que la empresa cumple con CMMI y es válido durante 3 años. Se realiza con un muestreo aleatorio de evidencias.
+ **Sustainment appraisal:** sirven para asegurar que se mantiene CMMI. Permite extender la validez del diploma otros 2 años. Se pueden realizar 3 antes de volver a hacer una auditoría Benchmark appraisal.
+ **Evaluation appraisal:** sirven para obtener una visión del estado de los procesos e identificar áreas de mejora. Se utilizan para evaluar el progreso de la implementación de CMMI.
$\space$
### 1.2.Técnicas de auditoría
Se utilizan principalmente dos técnicas:
+ Entrevistas.
+ Revisión de documentación.
$\space$
## 2.Quién realiza las auditorías?
No es el SEI el encargado de realizar las auditorías. Esta organización acredita a los auditores, conocidos como Lead Appraisers. Ellos se encargan de emitir los certificados a los auditados.

Tras realizar el Benchmark appraisal los LA envían documentación al SEI para que este asegure la calidad de la auditoría realizada. Si todo va bien se publican los resultados en el PARS (Published Appraisal Results).
$\space$
### 2.1.Participantes en un Benchmark appraisal
Los participantes son:
+ **Sponsor:** es el encargado del proyecto de mejora. Suele ser un directivo.
+ **Jefe del equipo de evaluación (ATL o Appraisal Team Leader):** es el responsable de realizar la evaluación.
+ **Miembros del equipo de evaluación (ATM o Appraisal Team Members):** es personal, tanto de la empresa como externo, con suficiente conocimiento y experiencia. Suelen ser entre 4 y 8 miembros.
+ **Coordinador de la organización (OUC o Organizational Unit Coordinator):** es el intermediario entre el equipo de evaluación y la empresa. Proporciona la información que solicita el evaluador. Suele ser el Responsable de Calidad.
+ **Participantes seleccionados:** es personal de la empresa que proporciona información durante la evaluación.
$\space$
#### 2.1.1.Requisitos para ser ATM
Se puede ser ATM de dos formas:
+ **Con capacitación previa en CMMI V1.3:** obteniendo el CMMI V2.0 Upgrade Training y pasando un examen para obtener el Certified CMMI Associate V2.0. Tiene una validez de 3 años tras pasar el examen.
+ **Sin capacitación previa en CMMI V1.3:** pasar el curso de Foundations of Capability, uno de los tres cursos específicos de las vistas Building Development Excellence, Building Service Development, o Building Supplier Management Excellence y pasando un examen para obtener el Certified CMMI Associate V2.0. Tiene una validez de 3 años tras pasar el examen.
$\space$
## 3.Qué se evalúa?
La empresa selecciona que PA y que PG evalúa.
$\space$
### 3.1.Partes evaluadas
Se evalúan:
+ **Unidad organizacional:** es la parte de la organización evaluada, por ejemplo, una serie de departamentos.
+ **Muestra de proyectos:** es una muestra representativa de los proyectos que se evalúan dentro de la unidad organizacional seleccionada.
$\space$
#### 3.1.1.Tipos de proyectos
Estos proyectos pueden ser:
+ **Proyectos objetivo:** proporcionan evidencias para todas las PA que se evalúan. Pueden ser proyectos en curso o acabados. Es obligatorio al menos uno.
+ **Proyectos no objetivo o de apoyo:** sirven como apoyo para proporcionar evidencias sobre algunas PA.
$\space$
## 4.Cómo se evalúa?
En las auditorías se comprueba que todos los PG de las PA han sido alcanzados. Para ello se comprueban las practices. 

Al realizar cada practice se produce documentación llamada evidencia objetiva. Son lo qué analiza el auditor durante la auditoría. Se deben guardar en una BBDD todas las evidencias objetivas llamada Base de Datos de Evidencias Objetivas.
$\space$
### 4.1.Tipos de evidencias objetivas
Pueden ser:
+ **Artefactos:** salidas producidas por la implementación de una practice. Por ejemplo, el plan de proyecto, documentación de estimaciones de trabajo, etc. 
+ **Afirmación:** confirmaciones que demuestran la implementación de una practice. Por ejemplo, cuestionarios, encuestas, etc.
$\space$
## 5.Fases de una auditoría

![[fases auditorías.png]]
$\space$
### 5.1.Fase pre On-site
La fase pre on-site es la primera fase, donde se planifica y prepara la auditoría.
$\space$
#### 5.1.1.Presentación
Se presenta unos 6 meses antes de comenzar las actividades On-site. El sponsor y el LA obtienen el compromiso de la gerencia y de la organización.
$\space$
#### 5.1.2.Planificación
Se planifican los ATM, la formación necesaria, se selecciona la unidad organizacional, se elige una muestra de proyectos, se planifica el calendario, se estiman riesgos y se imponen restricciones.

Se hace 4 meses antes de las actividades On-site. Lo hacen el sponsor, el LA y el OUC.
$\space$
#### 5.1.3.Preparación
Se realiza la formación, se elabora la BDEO, se hacen revisiones de preparación, se convoca a los participantes y se completa el plan de evaluación. Se hace entre 4 meses y 2 semanas antes de las actividades On-site. Lo hacen el sponsor, el LA y el OUC.
$\space$
### 5.2.Fase On-site
Se ejecuta el plan de evaluación copiando a un repositorio la información solicitada de la BDEO y el resto de información del sistema de calidad. Se realiza la revisión documental.

Por cada practice se pide un artefacto directo y uno indirecto o una afirmación. Participan el LA, la OUC, los ATM y los representantes seleccionados.
$\space$
#### 5.2.1.Resultados
Para cada practice se determina como se ha implementado:
+ **Fully implemented (FI):** sin debilidades, todo perfectamente presentado.
+ **Largely implemented (LI):** todo bien presentado, pero existe alguna debilidad.
+ **Partially implemented (PI):** no hay buenos artefactos directos o directamente no existen, pero hay evidencias que respaldan parte de la practice.
+ **Not implemented (NI):** no hay artefactos ni evidencias.
$\space$
#### 5.2.2.Evaluación
Los PG se evalúan como satisfechos o no satisfechos. Si todas las practices son FI o LI se considera el PG satisfecho, pero si la mayoría de las practices tienen debilidades, puede considerarse como no satisfecho.

