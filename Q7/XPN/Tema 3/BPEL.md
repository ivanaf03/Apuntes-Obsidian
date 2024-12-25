[[Tema 3-SOA y BPM]]

## Qué es BPEL?
> [!abstract] Definición de BPEL
> BPEL (Business Process Execution Language) es un lenguaje estándar basado en XML para la orquestación de procesos de negocio. 

Para implementar BPM es necesario un lenguaje estándar. Existen herramientas que permiten convertir el lenguaje en una notación más gráfica. Sin embargo, es mucho más simple que BPMN.

Se basa en la orquestación de servicios web para crear servicios web más grandes. Se ciñe completamente a backend.

### Elementos de BPEL
BPEL permite invocar servicios de forma secuencial o paralela. Consta de:
+ Condicionales.
+ Creación, copia y asignación de variables.
+ Bucles.
+ Manejadores de fallos.

### Procesos en BPEL
Un proceso BPEL está formado por:
+ **Archivo WSDL:** define su interfaz.
+ **Archivo BPEL:** define el proceso en el fichero XML.

## Estructura de un fichero BPEL
```xml
<process name="nameProcess" ...>
  <partnerLinks>
    <!-- Declaración de partner links -->
  </partnerLinks>
  <variables>
    <!-- Declaración de variables -->
  </variables>
  <sequence>
    <!-- Cuerpo principal de la definición del proceso BPEL -->
  </sequence>
</process>
```

### Partner links
> [!abstract] Definición de partner link
> Los partner links son representaciones de los clientes o servicios externos con los que nuestro proceso interactúa, ya sea para invocarlos o para que ellos nos inviten a interactuar.

Se declaran los clientes para permitir comunicaciones asíncronas. Cuando un cliente hace una solicitud al proceso, el proceso comienza la tarea, pero puede tardar un tiempo en terminarla. Cuando quiere devolverle el resultado, utiliza este partner link para devolvérselo a través de un callback.

### Ejemplo: reclamación de una póliza de seguro
El fichero WSDL podría ser algo así:

```xml
<definitions name="InsuranceClaim"
             targetNamespace="http://acm.org/samples"
             xmlns:tns="http://acm.org/samples"
             xmlns:plnk="http://schemas.xmlsoap.org/ws/2003/05/partner-link/"
             xmlns="http://schemas.xmlsoap.org/wsdl/"
             xmlns:bpws="http://schemas.xmlsoap.org/ws/2003/03/business-process/"
             xmlns:xsd="http://www.w3.org/2001/XMLSchema">

  <!-- Importa el archivo messages.wsdl para tener acceso al tipo de mensaje InsuranceClaimMsg -->
  <import namespace="http://acm.org/samples" location="messages.wsdl"/>

  <!-- Define el portType 'InsuranceClaim' con dos operaciones: 'initiate' y 'kill' -->
  <portType name="InsuranceClaim">
    <!-- Operación 'initiate': para iniciar una reclamación de seguro -->
    <operation name="initiate">
      <input message="tns:InsuranceClaimMsg"/>
    </operation>
    <!-- Operación 'kill': para cancelar o finalizar una reclamación de seguro -->
    <operation name="kill">
      <input message="tns:InsuranceClaimMsg"/>
    </operation>
  </portType>

  <!-- Define un tipo de partner link llamado 'InsuranceClaim' -->
  <plnk:partnerLinkType name="InsuranceClaim">
    <!-- Rol 'InsuranceClaimProvider': implementa el portType 'InsuranceClaim' -->
    <plnk:role name="InsuranceClaimProvider">
      <plnk:portType name="tns:InsuranceClaim"/>
    </plnk:role>
  </plnk:partnerLinkType>

</definitions>
```

El fichero BPEL podría ser algo así:

```xml
<process name="InsuranceClaim" ...>
  <!-- Partners en el proceso:
       - client: aplicación que puede iniciar y cancelar una reclamación.
       - evalWorklist: servicio llamado por este proceso para iniciar una tarea de flujo de trabajo humano que evalúe una reclamación.
       - anaWorklist: similar a evalWorklist, pero para el análisis de una reclamación.
       - esWorklist: similar, pero para la escalación de una reclamación.
  -->
  <partnerLinks>
    <partnerLink name="client" 
                 partnerLinkType="tns:InsuranceClaim" 
                 myRole="InsuranceClaimProvider"/>
    <partnerLink name="evalWorklist"
                 partnerLinkType="task:TaskManager"
                 partnerRole="TaskManager"
                 myRole="TaskManagerRequester"/>
    <partnerLink name="anaWorklist"
                 partnerLinkType="task:TaskManager"
                 partnerRole="TaskManager"
                 myRole="TaskManagerRequester"/>
    <partnerLink name="esWorklist"
                 partnerLinkType="task:TaskManager"
                 partnerRole="TaskManager"
                 myRole="TaskManagerRequester"/>
  </partnerLinks>

  <variables>
    <!-- Variable para almacenar el estado de la reclamación -->
    <variable name="status" type="xsd:string"/>
    <!-- Mensaje para iniciar una reclamación -->
    <variable name="initiateMsg" messageType="tns:InsuranceClaimMsg"/>
    <!-- Mensaje para cancelar o finalizar una reclamación -->
    <variable name="killEv" messageType="tns:InsuranceClaimMsg"/>
  </variables>

  <!-- Correlación de mensajes basada en el campo ClaimID -->
  <correlationSets>
    <correlationSet name="claim" properties="tns:claimID"/>
  </correlationSets>

  <sequence>
    <!-- Actividad de recepción: recibe el mensaje de inicio y realiza 
         la correlación basada en el set de correlación "claim" definido arriba -->
    <receive xmlns="http://schemas.xmlsoap.org/ws/2003/03/business-process/"
             partnerLink="client"
             portType="tns:InsuranceClaim"
             operation="initiate"
             variable="initiateMsg"
             createInstance="yes"
             name="initiateEvent">
      <correlations>
        <correlation set="claim" initiate="yes"/>
      </correlations>
    </receive>

    <!-- Asignar el estado inicial de la reclamación: "initiated" -->
    <assign name="setStatus">
      <copy>
        <from expression="string('initiated')"/>
        <to variable="status"/>
      </copy>
    </assign>
  </sequence>
</process>
```