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
ms.openlocfilehash: c8d9aa9fecff74a04e3f7cb395bffe5d239e18cf
ms.sourcegitcommit: 7791e470fc2e03bdf51b19a816d7215018772860
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "11387513"
---
# <a name="collect-and-use-diagnostic-information-from-hololens-devices"></a>Recopilar y usar información de diagnóstico de dispositivos HoloLens

Los usuarios y administradores de HoloLens pueden elegir entre cuatro métodos diferentes para recopilar información de diagnóstico de HoloLens:

- Aplicación centro de opiniones
- DiagnosticLog CSP
- Aplicación Configuración
- Diagnósticos sin conexión

> [!IMPORTANT]  
> Los registros de diagnóstico de dispositivos contienen información de identificación personal (PII), como sobre qué procesos o aplicaciones inicia el usuario durante las operaciones típicas. Cuando varios usuarios comparten un dispositivo HoloLens (por ejemplo, los usuarios inician sesión en el mismo dispositivo con diferentes cuentas de Microsoft Azure Active Directory (Azure AD) los registros de diagnóstico pueden contener información de PII que se aplica a varios usuarios. Para obtener más información, consulte [Declaración de privacidad de Microsoft](https://privacy.microsoft.com/privacystatement).

En la tabla siguiente se comparan distintos métodos de colección. Los nombres de método vinculan a información más detallada en las secciones que siguen a la tabla.

|Método |Requisitos previos |Ubicaciones de datos |Acceso y uso de datos |Retención de datos |
| --- | --- | --- | --- | --- |
|[Centro de opiniones](#feedback-hub) |Red e conexión a Internet<br /><br />Aplicación centro de opiniones<br /><br />Permiso para cargar archivos en la nube de Microsoft |Nube de Microsoft<br /><br />Dispositivo HoloLens (opcional) |El usuario solicita asistencia, acepta los términos de uso y carga los datos<br /><br />Los empleados de Microsoft ven los datos de forma coherente con los términos de uso |Los datos en la nube se conservan durante el período definido por la privacidad de próxima generación (NGP). A continuación, los datos se eliminan automáticamente.<br /><br />Los datos del dispositivo pueden ser eliminados en cualquier momento por un usuario que tenga permisos **de** administrador o propietario **del** dispositivo. |
|[Solucionador de problemas de configuración](#settings-troubleshooter) |Aplicación Configuración |Dispositivo HoloLens<br /><br />Equipo conectado (opcional) |El usuario almacena los datos y solo el usuario accede a los datos (a menos que el usuario comparta específicamente los datos con otro usuario). |Los datos se conservan en el dispositivo hasta que el usuario los elimina.* |
|[DiagnosticLog CSP](#diagnosticlog-csp) |Conexión de red<br /><br />Entorno MDM compatible con diagnosticLog CSP |El administrador configura las ubicaciones de almacenamiento |En el entorno administrado, el usuario acepta implícitamente el acceso de administrador a los datos.<br /><br />El administrador configura los roles y permisos de acceso. | Los datos se conservan en el almacenamiento en la nube y el administrador configura la directiva de retención. |
|[Diagnósticos sin conexión](#offline-diagnostics) |Configuración del dispositivo:<ul><li>Encendido y conectado al equipo</li><li>Botones de encendido y volumen funcionando</li></ul> |Dispositivo HoloLens<br /><br />Equipo conectado |El usuario almacena los datos y solo el usuario accede a los datos (a menos que el usuario comparta específicamente los datos con otro usuario). |Los datos se conservan en el dispositivo hasta que el usuario los elimina. |

- El usuario final es responsable de compartir los registros de forma responsable con otra persona. Estos archivos son principalmente útiles al ponerse en contacto con el servicio de atención al cliente y el soporte técnico.  

## <a name="feedback-hub"></a>Centro de opiniones

Un usuario de HoloLens puede usar la aplicación de escritorio de Microsoft Feedback Hub para enviar información de diagnóstico al soporte técnico de Microsoft. Para obtener información detallada e instrucciones completas, vea [Give us feedback](hololens-feedback.md).  

> [!NOTE]  
> **Usuarios comerciales o empresariales:** Si usas la aplicación Centro de opiniones para informar de un problema relacionado con MDM, el aprovisionamiento o cualquier otro aspecto de administración de dispositivos, cambia la categoría de la aplicación a categoría **Dispositivo**de administración  >  **empresarial.**

### <a name="prerequisites"></a>Requisitos previos

- El dispositivo está conectado a una red.
- La aplicación Centro de opiniones está disponible en el equipo de escritorio del usuario y el usuario puede cargar archivos en la nube de Microsoft.

### <a name="data-locations-access-and-retention"></a>Ubicaciones de datos, acceso y retención

Al aceptar los términos de uso del Centro de opiniones, el usuario consiente explícitamente el almacenamiento y el uso de los datos (tal como se define en dicho contrato).

El Centro de opiniones proporciona dos lugares para que el usuario almacene información de diagnóstico:

- **La nube de Microsoft**. Los datos que el usuario carga mediante la aplicación Centro de opiniones se almacenan durante el número de días que son coherentes con los requisitos de privacidad de próxima generación (NGP). Los empleados de Microsoft pueden usar un visor compatible con NGP para acceder a la información durante este período.
   > [!NOTE]  
   > Estos requisitos se aplican a los datos de todas las categorías del Centro de opiniones.

- **El dispositivo HoloLens**. Al archivar un informe en el Centro de opiniones, el usuario puede seleccionar Guardar una copia local de diagnósticos y datos **adjuntos creados al enviar comentarios.** Si el usuario selecciona esta opción, el Centro de opiniones almacena una copia de la información de diagnóstico en el dispositivo HoloLens. Esta información sigue siendo accesible para el usuario (o cualquier persona que use esa cuenta para iniciar sesión en HoloLens). Para eliminar esta información, un usuario **** debe tener permisos **de** administrador o propietario del dispositivo en el dispositivo. Un usuario que tenga los permisos adecuados puede **** iniciar sesión en el Centro de comentarios, seleccionar Configuración Ver registros de diagnóstico  >  **y**eliminar la información.

## <a name="settings-troubleshooter"></a>Solucionador de problemas de configuración

Un usuario de HoloLens puede usar la aplicación Configuración del dispositivo para solucionar problemas y recopilar información de diagnóstico. Para ello, sigue estos pasos:

1. Abre la aplicación Configuración y selecciona **Actualizar & solución de problemas**  >  **de** seguridad.
1. Seleccione el área adecuada y seleccione **Inicio**.
1. Reproduce el problema.
1. Después de reproducir el problema, vuelva a Configuración y, a continuación, seleccione **Detener**.

### <a name="prerequisites"></a>Requisitos previos

- La aplicación Configuración está instalada en el dispositivo y está disponible para el usuario.

### <a name="data-locations-access-and-retention"></a>Ubicaciones de datos, acceso y retención

Dado que el usuario inicia la recopilación de datos, el usuario acepta implícitamente el almacenamiento de la información de diagnóstico. Solo el usuario, o cualquier persona con la que el usuario comparte los datos, puede acceder a los datos.

La información de diagnóstico se almacena en el dispositivo. Si el dispositivo está conectado al equipo del usuario, la información también reside en el equipo en el siguiente archivo:

> Este equipo\\ \<*HoloLens device name*> \\Almacenamiento interno\\Documents\\Trace \<*ddmmyyhhmmss*> .etl

> [!NOTE]  
> En esta ruta de acceso y nombre de archivo, representa el nombre del dispositivo HoloLens y representa la fecha y hora \<*HoloLens device name*> \<*ddmmyyhhmmss*> en que se creó el archivo.

La información de diagnóstico permanece en estas ubicaciones hasta que el usuario la elimina.

## <a name="diagnosticlog-csp"></a>DiagnosticLog CSP

En un entorno de administración de dispositivos móviles (MDM), el administrador de TI puede usar el proveedor de servicios de configuración [diagnosticLog (CSP)](https://docs.microsoft.com/windows/client-management/mdm/diagnosticlog-csp) para configurar las opciones de diagnóstico en dispositivos HoloLens inscritos. El administrador de TI puede configurar estas opciones para recopilar registros de dispositivos inscritos.

### <a name="prerequisites"></a>Requisitos previos

- El dispositivo está conectado a una red.
- El dispositivo está inscrito en un entorno MDM compatible con diagnosticLog CSP.

### <a name="data-locations-access-and-retention"></a>Ubicaciones de datos, acceso y retención

Dado que el dispositivo forma parte del entorno administrado, el usuario acepta implícitamente el acceso administrativo a la información de diagnóstico.

El administrador de TI usa diagnosticLog CSP para configurar las directivas de almacenamiento, retención y acceso de datos, incluidas las directivas que rigen lo siguiente:

- La infraestructura en la nube que almacena la información de diagnóstico.
- Período de retención de la información de diagnóstico.
- Permisos que controlan el acceso a la información de diagnóstico.

## <a name="offline-diagnostics"></a>Diagnósticos sin conexión
En situaciones en las que el dispositivo no puede recopilar diagnósticos mediante el Centro de opiniones o el solucionador de problemas de configuración, puedes recopilar diagnósticos manualmente. Un escenario en el que esto es necesario es cuando el dispositivo no puede conectarse a Wi-Fi o no se puede acceder a otros métodos mencionados anteriormente. Los diagnósticos recopilan volcados de memoria y registros del dispositivo que ayudan a un ingeniero de soporte técnico de Microsoft a aislar problemas.

Esto funciona cuando el dispositivo aparece en el Explorador de archivos después de conectarlo a un equipo a través de un cable USB.

> [!NOTE]
> La generación y administración de diagnósticos sin conexión se controla de forma diferente en función de la versión del sistema operativo. Anteriormente se controlaba mediante la configuración de telemetría, pero ahora se controla directamente a través de la directiva MDM. Si se deshabilita mediante la configuración o la directiva MDM, los registros de diagnóstico no se pueden recopilar con este mecanismo.

Comportamiento anterior a [Windows Holographic, verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2):
 - El diagnóstico sin conexión solo está habilitado cuando el usuario pasa por OOBE o el valor de directiva [System\AllowTelemetry](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry) se establece en Full (Basic es el valor predeterminado en HoloLens). 
- Para deshabilitar el diagnóstico sin conexión, vaya a Configuración **de la aplicación > privacidad** y seleccione Básico **en** Datos **de diagnóstico**. En las compilaciones en las que el diagnóstico sin conexión depende de la configuración de telemetría, solo afecta si se recopilan o no registros. No afecta a los archivos que se recopilan.
- Si el dispositivo está bloqueado, los registros no aparecerán.

En crea [Windows Holographic, verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2) y versiones 2:
- Cuando el diagnóstico de reserva esté habilitado, se controlará mediante una directiva MDM específica con la configuración [correspondiente MixedReality/FallbackDiagnostics](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-fallbackdiagnostics)
- Si el dispositivo está bloqueado, los registros no aparecerán.

Vea este vídeo para obtener más información.

> [!VIDEO https://channel9.msdn.com/Shows/Docs-Mixed-Reality/Gathering-Diagnostic-Files-on-HoloLens2/player]

Siga estos pasos para recopilar diagnósticos:
1.  Conecta el dispositivo con un cable USB a tu PC.
2.  En el Explorador de archivos del equipo, vaya a **"Este equipo \<hololens-device> \Almacenamiento interno".**
3.  Si la **carpeta Almacenamiento** interno no aparece, el dispositivo espera a que un usuario inicie sesión. Inicie sesión o encienda el dispositivo manteniendo presionado el botón POWER durante 10 segundos.
4.  Presione y suelte inmediatamente los **botones POWER + VOLUME DOWN** juntos.
5.  Espere un minuto para que el dispositivo prepare los archivos zip. (Un archivo temporal denominado HololensDiagnostics.temp puede quedar visible mientras el dispositivo genera los archivos zip. No acceda ni guarde ese archivo. Cuando finalice el proceso, se reemplazará por los archivos zip).
6.  Actualice el explorador de archivos y vaya a la **carpeta '\Documents'.**
7.  Copie los archivos ZIP de diagnóstico y compárense con el equipo de soporte técnico de Microsoft.

> [!NOTE]
> Algunos de los archivos ZIP de diagnóstico pueden contener información de identificación personal.