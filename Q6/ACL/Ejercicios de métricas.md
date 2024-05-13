[[Aseguramento da calidade]]
$\space$
## 1.Defina, en una plantilla, una métrica que permita conocer el grado de cumplimiento actual de los costes definidos en el Plan de proyecto

| 1                      | Cumplimiento de hitos                                                                                                                                                                                                                                                                                                                                                                 |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Objetivo:              | Conocer el grado de cumplimiento actual de los costes definidos en el Plan de Proyecto                                                                                                                                                                                                                                                                                                |
| Fórmula:               | CosteActual / CostePlanificado  x 100                                                                                                                                                                                                                                                                                                                  |
| Unidad de medida:      | % |
| Unidad de medida:      | %                                                                                                                                                                                                                                                                                                                                                                                     |
| Origen de los datos:   | Plan de proyecto                                                                                                                                                                                                                                                                                                                                                                      |
| Periocididad:          | Seguimiento                                                                                                                                                                                                                                                                                                                                                                           |
| Criterios de análisis: | Un crecimiento no proporcional con el porcentaje del completitud del proyecto indica desviaciones en el coste. Si se detecta un crecimiento muy rápido del porcentaje se deben tomar acciones preventivas para reducir los costes. Si se detecta que el porcentaje se acerca al 100% antes del final del proyecto se deben tomar acciones correctivas.                                |
$\space$
## 2.Defina, en una plantilla, una métrica que permita conocer el nivel de productividad de los programadores de un proyecto en comparación con otros proyectos de la empresa

| 2                      | Cumplimiento de hitos                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| ---------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Objetivo:              | Conocer el nivel de productividad de los programadores de un proyecto en comparación con otros proyectos de la empresa                                                                                                                                                                                                                                                                                                                                                              |
| Fórmula:               | PuntosFunciónCompletados / PuntoFunciónPlanificados x 100                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Unidad de medida:      | %                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Origen de los datos:   | Plan de proyecto                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| Periocididad:          | Seguimiento                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Criterios de análisis: | Un programador con alto porcentaje en un proyecto suele estar realizando tareas en las que es muy productivo. Si se detecta que un programador tiene un alto porcentaje en un proyecto y bajo porcentaje en otro, se le asignarán más tareas del primero y se reducirán proporcionalmente las tareas del segundo. Para no afectar a la duración de los proyectos se reasignarán también las horas de otro programador de forma inversa basándose en los resultados de esta métrica. |
$\space$
## 3.Defina, en una plantilla, una métrica que permita conocer el grado de implementación de los casos de uso previstos para la iteración actual

| 3                      | Cumplimiento de hitos                                                                                               |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------- |
| Objetivo:              | Conocer el grado de implementación de los casos de uso previstos para la iteración actual                           |
| Fórmula:               | NúmeroCUImplementados / TotalCU  x 100                                                                              |
| Unidad de medida:      | %                                                                                                                   |
| Origen de los datos:   | ERS                                                                                                                 |
| Periocididad:          | Seguimiento                                                                                                         |
| Criterios de análisis: | Cuanto mayor sea el porcentaje, más cerca se está de cumplir con los requisitos funcionales pedidos por el cliente. |
$\space$
## 4.Defina, en una plantilla, una métrica que permita conocer el tiempo medio invertido en las revisiones de progreso del proyecto
| 4                      | Cumplimiento de hitos                                                                                                                                   |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Objetivo:              | Conocer el tiempo medio invertido en las revisiones de progreso del proyecto                                                                            |
| Fórmula:               | SumatorioTiempoRevisiones / NúmeroRevisiones                                                                                                            |
| Unidad de medida:      | Horas                                                                                                                                                   |
| Origen de los datos:   | Seguimiento                                                                                                                                             |
| Periocididad:          | Al cerrar el proyecto                                                                                                                                   |
| Criterios de análisis: | Si alguna de las revisiones de un proyecto ha durado una cantidad de horas muy diferente de la media se debe revisar cual fue el motivo y justificarlo. |
$\space$
## 5.Defina, en una plantilla, una métrica que permita determinar el grado de criticidad de un proyecto
| 5                      | Cumplimiento de hitos                                                                                                                                                                                                                             |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Objetivo:              | Determinar el grado de criticidad de un proyecto                                                                                                                                                                                                  |
| Fórmula:               | Número de tareas críticas                                                                                                                                                                                                                         |
| Unidad de medida:      | Valor numérico                                                                                                                                                                                                                                    |
| Origen de los datos:   | Plan de proyecto                                                                                                                                                                                                                                  |
| Periocididad:          | Seguimiento                                                                                                                                                                                                                                       |
| Criterios de análisis: | La frecuencia del riesgo puede ser (0, 0.25, 0.5, 0.75 o 1) y el impacto de las consecuencias se mide del 1 al 5, siendo 1 un riesgo asumible y 5 un riesgo perjudicial para el proyecto. Cuanto mayor sea el número, más crítico es el proyecto. |
$\space$
## 6.Defina, en una plantilla, una métrica que permita detectar el grado de desviación en tareas críticas de un proyecto

| 6                      | Cumplimiento de hitos                                                                                                                                    |
| ---------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Objetivo:              | Detectar el grado de desviación en tareas críticas de un proyecto                                                                                        |
| Fórmula:               | (TiempoRealTareasCríticas -  TiempoPlanificadoTareasCríticas) / TiempoPlanificadoTareasCríticas x 100                                                    |
| Unidad de medida:      | %                                                                                                                                                        |
| Origen de los datos:   | Plan de proyecto                                                                                                                                         |
| Periocididad:          | Seguimiento                                                                                                                                              |
| Criterios de análisis: | Un porcentaje positivo indica desviaciones en las tareas críticas y, por tanto, aumento de la duración del camino crítico y de la duración del proyecto. |
$\space$
## 7.Defina, en una plantilla, una métrica que permita conocer el grado de acoplamiento entre las clases de diseño en un proyecto

| 7                      | Cumplimiento de hitos                                                                                       |
| ---------------------- | ----------------------------------------------------------------------------------------------------------- |
| Objetivo:              | Conocer el grado de acoplamiento entre las clases de diseño en un proyecto                                  |
| Fórmula:               | NúmeroClasesExternasReferenciadasPorLaClase / TotalClases                                                   |
| Unidad de medida:      | Valor numérico                                                                                              |
| Origen de los datos:   | Diagramas de diseño de bajo nivel                                                                           |
| Periocididad:          | Fase de diseño de bajo nivel                                                                                |
| Criterios de análisis: | Cuanto mayor sea el valor, mayor será el acoplamiento de la clase con otras clases del sistema y viceversa. |
$\space$
## 8.Defina, en una plantilla, una métrica que permita conocer el grado de compleción de los requisitos iniciales de un proyecto
| 8                      | Cumplimiento de hitos                                                                                                |
| ---------------------- | -------------------------------------------------------------------------------------------------------------------- |
| Objetivo:              | Conocer el grado de compleción de los requisitos iniciales de un proyecto                                            |
| Fórmula:               | NúmeroRequisitosCompletados / TotalRequisitosIniciales  x 100                                                        |
| Unidad de medida:      | %                                                                                                                    |
| Origen de los datos:   | ERS                                                                                                                  |
| Periocididad:          | Seguimiento                                                                                                          |
| Criterios de análisis: | Una vez se alcance el 100% se habrán completado todos los requisitos sugeridos por el cliente en la primera reunión. |
Nota: otro campo útil en la plantilla sería el encargado de tomar la métrica.