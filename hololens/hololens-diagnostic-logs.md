---
title: Recopilar y usar información de diagnóstico de dispositivos HoloLens
description: Aprende a recopilar, usar y conservar información de diagnóstico de dispositivos HoloLens.
author: Teresa-Motiv
ms.author: v-tea
ms.date: 10/15/2020
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
ms.topic: article
ms.custom:
- CI 115131
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: medium
keywords: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 206a31476820e8722b1b72fbd501345a089379b1
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283231"
---
# Recopilar y usar información de diagnóstico de dispositivos HoloLens

Los usuarios y administradores de HoloLens pueden elegir entre cuatro métodos diferentes para recopilar información de diagnóstico de HoloLens:

- Aplicación Centro de opiniones
- DiagnosticLog CSP
- Aplicación Configuración

> [!IMPORTANT]  
> Los registros de diagnóstico de dispositivos contienen información de identificación personal (PII), como sobre qué procesos o aplicaciones inicia el usuario durante las operaciones típicas. Cuando varios usuarios comparten un dispositivo HoloLens (por ejemplo, los usuarios inician sesión en el mismo dispositivo con diferentes cuentas de Microsoft Azure Active Directory (Azure AD), los registros de diagnóstico pueden contener información de PII que se aplica a varios usuarios. Para obtener más información, vea la [declaración de privacidad de Microsoft.](https://privacy.microsoft.com/privacystatement)

En la tabla siguiente se comparan los tres métodos de colección. Los nombres de los métodos se vinculan a información más detallada en las secciones que siguen a la tabla.

|Método |Requisitos previos |Ubicaciones de datos |Acceso y uso de datos |Retención de datos |
| --- | --- | --- | --- | --- |
|[Centro de opiniones](#feedback-hub) |Red e conexión a Internet<br /><br />Aplicación Centro de opiniones<br /><br />Permiso para cargar archivos en la nube de Microsoft |Nube de Microsoft<br /><br />Dispositivo HoloLens (opcional) |El usuario solicita asistencia, acepta los términos de uso y carga los datos<br /><br />Los empleados de Microsoft ven los datos de forma coherente con los términos de uso |Los datos en la nube se conservan durante el período definido por la privacidad de próxima generación (NGP). A continuación, los datos se eliminan automáticamente.<br /><br />Los datos del dispositivo pueden ser eliminados en cualquier momento por un usuario que tenga permisos **de** administrador o propietario **del** dispositivo. |
|[Solucionador de problemas de configuración](#settings-troubleshooter) |Aplicación Configuración |Dispositivo HoloLens<br /><br />Equipo conectado (opcional) |El usuario almacena los datos y solo el usuario tiene acceso a los datos (a menos que el usuario comparta específicamente los datos con otro usuario). |Los datos se conservan hasta que el usuario los elimina.* |
|[DiagnosticLog CSP](#diagnosticlog-csp) |Conexión de red<br /><br />Entorno MDM que admite diagnosticLog CSP |El administrador configura las ubicaciones de almacenamiento |En el entorno administrado, el usuario acepta implícitamente el acceso de administrador a los datos.<br /><br />El administrador configura los roles y permisos de acceso. | El administrador configura la directiva de retención. |
|[Diagnósticos sin conexión](#offline-diagnostics) |Configuración del dispositivo:<ul><li>Encendido y conectado al equipo</li><li>Botones de energía y volumen en funcionamiento</li></ul> |Dispositivo HoloLens<br /><br />Equipo conectado |El usuario almacena los datos y solo el usuario accede a los datos (a menos que el usuario comparta específicamente los datos con otro usuario). |Los datos se conservan hasta que el usuario los elimina. | 


-   El usuario final es responsable de compartir los registros de forma responsable con otra persona. Estos archivos son principalmente útiles al ponerse en contacto con el servicio de soporte técnico y atención al cliente.  

## Centro de opiniones

Un usuario de HoloLens puede usar la aplicación de escritorio del Centro de opiniones de Microsoft para enviar información de diagnóstico al soporte técnico de Microsoft. Para obtener información detallada e instrucciones completas, consulte [Enviarnos comentarios.](hololens-feedback.md)  

> [!NOTE]  
> **Usuarios comerciales o empresariales:** Si usas la aplicación Centro de opiniones para informar de un problema relacionado con MDM, el aprovisionamiento o cualquier otro aspecto de administración de dispositivos, cambia la categoría de la aplicación a la categoría dispositivo de administración ****  >  **empresarial.**

### Requisitos previos

- El dispositivo está conectado a una red.
- La aplicación Centro de opiniones está disponible en el equipo de escritorio del usuario y el usuario puede cargar archivos en la nube de Microsoft.

### Ubicaciones de datos, acceso y retención

Al aceptar los términos de uso del Centro de opiniones, el usuario consiente explícitamente el almacenamiento y el uso de los datos (según se define en dicho acuerdo).

El Centro de opiniones proporciona dos lugares para que el usuario almacene información de diagnóstico:

- **La nube de Microsoft**. Los datos que el usuario carga mediante la aplicación Centro de opiniones se almacenan durante el número de días que es coherente con los requisitos de privacidad de próxima generación (NGP). Los empleados de Microsoft pueden usar un visor compatible con NGP para acceder a la información durante este período.
   > [!NOTE]  
   > Estos requisitos se aplican a los datos de todas las categorías del Centro de opiniones.

- **El dispositivo HoloLens**. Al archivar un informe en el Centro de opiniones, el usuario puede seleccionar Guardar una copia local de diagnósticos y datos **adjuntos creados al enviar comentarios.** Si el usuario selecciona esta opción, el Centro de opiniones almacena una copia de la información de diagnóstico en el dispositivo HoloLens. Esta información sigue siendo accesible para el usuario (o cualquier persona que use esa cuenta para iniciar sesión en HoloLens). Para eliminar esta información, un usuario **** debe tener permisos de propietario **del** dispositivo o administrador en el dispositivo. Un usuario que tenga los permisos adecuados puede **** iniciar sesión en el Centro de  >  **opiniones,** seleccionar los registros de diagnóstico de vista de configuración y eliminar la información.

## Solucionador de problemas de configuración

Un usuario de HoloLens puede usar la aplicación Configuración en el dispositivo para solucionar problemas y recopilar información de diagnóstico. Para ello, sigua estos pasos:

1. Abre la aplicación Configuración y selecciona Actualizar & **solución de problemas**  >  **de** seguridad.
1. Seleccione el área adecuada y seleccione **Inicio**.
1. Reproduzca el problema.
1. Después de reproducir el problema, vuelva a Configuración y, a continuación, seleccione **Detener**.

### Requisitos previos

- La aplicación Configuración está instalada en el dispositivo y está disponible para el usuario.

### Ubicaciones de datos, acceso y retención

Dado que el usuario inicia la recopilación de datos, el usuario acepta implícitamente el almacenamiento de la información de diagnóstico. Solo el usuario, o cualquier persona con quien el usuario comparta los datos, puede tener acceso a los datos.

La información de diagnóstico se almacena en el dispositivo. Si el dispositivo está conectado al equipo del usuario, la información también reside en el equipo en el siguiente archivo:

> Este equipo\\ \<*HoloLens device name*> \\Almacenamiento interno\\Documentos\\Seguimiento \<*ddmmyyhhmmss*> .etl

> [!NOTE]  
> En esta ruta de acceso y nombre de archivo, representa el nombre del dispositivo HoloLens y representa la fecha y la hora en \<*HoloLens device name*> \<*ddmmyyhhmmss*> que se creó el archivo.

La información de diagnóstico permanece en estas ubicaciones hasta que el usuario la elimina.

## DiagnosticLog CSP

En un entorno de administración de dispositivos móviles (MDM), el administrador de TI puede usar el proveedor de servicios de configuración [(CSP) DiagnosticLog](https://docs.microsoft.com/windows/client-management/mdm/diagnosticlog-csp) para configurar las opciones de diagnóstico en dispositivos HoloLens inscritos. El administrador de TI puede configurar estas opciones para recopilar registros de dispositivos inscritos.

### Requisitos previos

- El dispositivo está conectado a una red.
- El dispositivo está inscrito en un entorno MDM que admite diagnosticLog CSP.

### Ubicaciones de datos, acceso y retención

Dado que el dispositivo forma parte del entorno administrado, el usuario acepta implícitamente el acceso administrativo a la información de diagnóstico.

El administrador de TI usa diagnosticLog CSP para configurar las directivas de almacenamiento, retención y acceso de datos, incluidas las directivas que rigen lo siguiente:

- La infraestructura de nube que almacena la información de diagnóstico.
- Período de retención de la información de diagnóstico.
- Permisos que controlan el acceso a la información de diagnóstico.

## Diagnósticos sin conexión
En situaciones en las que el dispositivo no puede recopilar diagnósticos mediante el Centro de opiniones o el Solucionador de problemas de configuración, puedes recopilar diagnósticos manualmente. Un escenario en el que esto es necesario es cuando el dispositivo no se puede conectar a una red Wi-Fi. Los diagnósticos recopilan volcados de memoria y registros del dispositivo que ayudan a un ingeniero de soporte técnico de Microsoft a aislar los problemas.

Esto funciona cuando el dispositivo se muestra en el Explorador de archivos después de conectarlo a un equipo a través de un cable USB. 

> [!NOTE]
> La generación y administración de diagnósticos sin conexión se controla de forma diferente en función de la versión del sistema operativo. Anteriormente se controlaba mediante la configuración de telemetría, pero ahora se controla directamente a través de la directiva. 

Comportamiento anterior a [Windows Holographic, verison 20H2:](hololens-release-notes.md#windows-holographic-version-20h2)
 - El diagnóstico sin conexión solo está habilitado cuando el usuario está pasando por la OOBE o system\El valor de la directiva [AllowTelemetry](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry) está establecido en Completo (Basic es el valor predeterminado en HoloLens). 
- Para deshabilitar el diagnóstico sin conexión, vaya a Configuración **de la > privacidad** y seleccione **Básica** en Datos **de diagnóstico.** En las compilaciones en las que el diagnóstico sin conexión depende de la configuración de telemetría, solo afecta si se recopilan o no registros. No afecta a los archivos que se recopilan.
- Si el dispositivo está bloqueado, los registros no aparecerán.

En compilaciones [de Windows Holographic, verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2) y posterior:
- Cuando el diagnóstico de reserva está habilitado, se controlará mediante una directiva MDM específica con la configuración [correspondiente MixedReality/FallbackDiagnostics](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-fallbackdiagnostics)
- Si el dispositivo está bloqueado, los registros no aparecerán.


Vea este vídeo para obtener más información. 

> [!VIDEO https://channel9.msdn.com/Shows/Docs-Mixed-Reality/Gathering-Diagnostic-Files-on-HoloLens2/player]

Siga estos pasos para recopilar diagnósticos:
1.  Conecta el dispositivo con un cable USB al equipo.
2.  En el Explorador de archivos de tu equipo, ve a **"Este equipo \<hololens-device> \Almacenamiento interno".**
3.  Si no **se muestra la** carpeta Almacenamiento interno, el dispositivo espera a que un usuario inicie sesión. Inicie sesión o encienda el dispositivo manteniendo presionado el botón DE ENCENDIDO durante 10 segundos.
4.  Presiona y suelta inmediatamente los botones **POWER + VOLUME DOWN** juntos.
5.  Espere un minuto para que el dispositivo prepare los archivos zip. (Un archivo temporal denominado HololensDiagnostics.temp puede hacerse visible mientras el dispositivo genera los archivos zip. No obtenga acceso a ese archivo ni guárdelo. Cuando finalice el proceso, se reemplazará por los archivos zip).
6.  Actualice el explorador de archivos y vaya a la **carpeta "\Documentos".**
7.  Copie los archivos ZIP de diagnóstico y compártolos con el equipo de soporte técnico de Microsoft.

> [!NOTE]
> Algunos de los archivos ZIP de diagnóstico pueden contener información de identificación personal.



