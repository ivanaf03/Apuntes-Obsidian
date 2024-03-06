[[Tema 4-Capa de servicios REST con Spring]]

# 1.Mensajes de error
Los mensajes de error deben ir en el idioma que prefiera el usuario. La emisión de mensajes en un idioma concreto se denomina `i18n` o internacionalización. Se hace mediante `locale`.

Además se deben internacionalizar las entradas y salidas de datos numéricos, fechas, cantidades monetarias, etc.

## 1.1.Locale
Consiste en una abstracción de idioma, país y variante. En java se utiliza el paquete `java.util.Locale`.

## 1.2.Caso de estudio
Lo backend solo gestionará la internacionalización de los mensajes. En frontend se encargará de formateo de fechas y cantidades numéricas. Por simplicidad no se internacionaliza la base de datos.

Con Spring tenemos que crear ficheros `properties` con formato `clave=texto del mensaje`. Tienen que estar en el mismo path. Usa el bean de tipo `MessageSource` para recuperar mensajes en un locale concreto a partir de su clave.

# 2.Peticiones HTTP
Los navegadores pueden enviar peticiones HTTP con la cabecera `Accept-Language`. Es una lista priorizada de los lenguajes que quiere el usuario mediante la configuración del navegador o del SO.

