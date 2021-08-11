---
title: Recopilación y uso de la información de diagnóstico de dispositivos HoloLens
description: Obtenga información sobre cómo recopilar, usar y conservar información de diagnóstico de HoloLens dispositivos.
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
ms.openlocfilehash: 96fe9492da035747a22123ee1cd0c1481cd821a4f2e549b6414a21810ec268d6
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665308"
---
# <a name="collect-and-use-diagnostic-information-from-hololens-devices"></a>Recopilación y uso de la información de diagnóstico de dispositivos HoloLens

HoloLens usuarios y administradores pueden elegir entre cuatro métodos diferentes para recopilar información de diagnóstico de HoloLens:

- Centro de opiniones aplicación
- DiagnosticLog CSP
- Aplicación Configuración
- Diagnósticos sin conexión

> [!IMPORTANT]  
> Los registros de diagnóstico de dispositivos contienen información de identificación personal (PII), como qué procesos o aplicaciones inicia el usuario durante las operaciones típicas. Cuando varios usuarios comparten un dispositivo HoloLens (por ejemplo, los usuarios inician sesión en el mismo dispositivo con diferentes cuentas de Microsoft Azure Active Directory (Azure AD), los registros de diagnóstico pueden contener información de PII que se aplica a varios usuarios. Para obtener más información, vea [Declaración de privacidad de Microsoft](https://privacy.microsoft.com/privacystatement).

En la tabla siguiente se comparan distintos métodos de colección. Los nombres de método se vinculan a información más detallada en las secciones que siguen a la tabla.

|Método |Requisitos previos |Ubicaciones de datos |Acceso y uso de datos |Retención de datos |
| --- | --- | --- | --- | --- |
|[Centro de opiniones](#feedback-hub) |Red e conexión a Internet<br /><br />Centro de opiniones aplicación<br /><br />Permiso para cargar archivos en la nube de Microsoft |Servicios en la nube de Microsoft<br /><br />HoloLens dispositivo (opcional) |El usuario solicita asistencia, acepta los términos de uso y carga los datos.<br /><br />Los empleados de Microsoft ven los datos de forma coherente con los términos de uso. |Los datos en la nube se conservan durante el período definido por la privacidad de próxima generación (NGP). A continuación, los datos se eliminan automáticamente.<br /><br />Los datos del dispositivo pueden ser eliminados en cualquier momento por un usuario que tenga permisos **de** administrador o **propietario** del dispositivo. |
|[Configuración Solucionador](#settings-troubleshooter) |Aplicación Configuración |Dispositivo HoloLens<br /><br />Equipo conectado (opcional) |El usuario almacena los datos y solo el usuario accede a los datos (a menos que el usuario comparta específicamente los datos con otro usuario). |Los datos se conservan en el dispositivo hasta que el usuario los elimina.* |
|[DiagnosticLog CSP](#diagnosticlog-csp) |Conexión de red<br /><br />Entorno MDM que admite diagnosticLog CSP |El administrador configura las ubicaciones de almacenamiento |En el entorno administrado, el usuario da su consentimiento implícitamente para el acceso de administrador a los datos.<br /><br />El administrador configura los roles y permisos de acceso. | Los datos se conservan en el almacenamiento en la nube y el administrador configura la directiva de retención. |
|[Diagnósticos sin conexión](#offline-diagnostics) |Configuración del dispositivo:<ul><li>Encendido y conectado al equipo</li><li>Botones de encendido y volumen en funcionamiento</li></ul> |Dispositivo HoloLens<br /><br />Equipo conectado |El usuario almacena los datos y solo el usuario accede a los datos (a menos que el usuario comparta específicamente los datos con otro usuario). |Los datos se conservan en el dispositivo hasta que el usuario los elimina. |

* El usuario final es responsable de compartir los registros de forma responsable con otra persona. Estos archivos son principalmente útiles al ponerse en contacto con el servicio de atención al cliente y el soporte técnico.  

## <a name="feedback-hub"></a>Centro de opiniones

Un HoloLens usuario puede usar la aplicación de escritorio microsoft Centro de opiniones para enviar información de diagnóstico a Soporte técnico de Microsoft. Para obtener más información e instrucciones completas, vea [Enviarnos comentarios.](hololens-feedback.md)  

> [!NOTE]  
> **Usuarios comerciales o empresariales:** Si usa la aplicación Centro de opiniones para notificar un problema relacionado con MDM, el aprovisionamiento o cualquier otro aspecto de administración de dispositivos, cambie la categoría de la aplicación a Enterprise **categoría** Dispositivo de  >  **administración**.

>[!IMPORTANT]
> Para proporcionar los mejores datos posibles para corregir problemas, se recomienda encarecidamente establecer la telemetría del dispositivo en **Opcional.** Puede establecer este valor durante la experiencia rápida (OOBE) o mediante la aplicación **Configuración** configuración. Para ello mediante el uso de Configuración, seleccione **Start > Configuración > Privacy > App Diagnostics > On**(Iniciar > Configuración > diagnósticos de > aplicación de > en ).
### <a name="prerequisites"></a>Requisitos previos

- El dispositivo está conectado a una red.
- La Centro de opiniones está disponible en el equipo de escritorio del usuario y el usuario puede cargar archivos en la nube de Microsoft.

### <a name="data-locations-access-and-retention"></a>Ubicaciones, acceso y retención de datos

Al aceptar los términos de uso del Centro de opiniones, el usuario da su consentimiento explícitamente para el almacenamiento y el uso de los datos (tal como se define en ese contrato).

El Centro de opiniones proporciona dos lugares para que el usuario almacene información de diagnóstico:

- **La nube de Microsoft**. Los datos que el usuario carga mediante la aplicación Centro de opiniones se almacenan durante el número de días que es coherente con los requisitos de privacidad de próxima generación (NGP). Los empleados de Microsoft pueden usar un visor compatible con NGP para acceder a la información durante este período.

   > [!NOTE]  
   > Estos requisitos se aplican a los datos de todas Centro de opiniones categorías.

- **El HoloLens .** Al presentar un informe en Centro de opiniones, el usuario puede seleccionar Guardar una copia local de diagnósticos y datos **adjuntos creados al proporcionar comentarios.** Si el usuario selecciona esta opción, el Centro de opiniones almacena una copia de la información de diagnóstico en el HoloLens dispositivo. Esta información sigue siendo accesible para el usuario (o cualquier persona que use esa cuenta para iniciar sesión en HoloLens). Para eliminar esta información, un usuario  debe tener permisos **de** administrador o propietario del dispositivo en el dispositivo. Un usuario que tenga los permisos adecuados puede iniciar sesión en el Centro de opiniones, seleccionar Configuración Ver registros de diagnóstico y  >  eliminar la información.

## <a name="settings-troubleshooter"></a>Configuración Solucionador

Un HoloLens usuario puede usar la **aplicación Configuración** en el dispositivo para solucionar problemas y recopilar información de diagnóstico. Para ello, realice los pasos siguientes:

1. Abra la aplicación Configuración y seleccione Actualizar & **solución de problemas**  >  **de** seguridad.
1. Seleccione el área adecuada y seleccione **Iniciar.**
1. Reproduzca el problema.
1. Después de reproducir el problema, vuelva a Configuración y, a continuación, seleccione **Detener**.

Un usuario también puede configurar el comportamiento de los diagnósticos de reserva desde **Configuración** aplicación. Vaya a **la página privacidad -> solución de problemas** para configurar esta opción.
> [!NOTE]
> Si hay una directiva MDM configurada para el dispositivo, el usuario no podrá invalidar ese comportamiento.

### <a name="os-update-troubleshooter"></a>Solucionador de problemas de actualización del sistema operativo
En las [compilaciones Windows Holographic, versión 21H1](hololens-release-notes.md#windows-holographic-version-21h1) y versiones adelante:
- Además de los solucionadores de problemas anteriores dentro de la aplicación Configuración, se ha agregado un nuevo solucionador de problemas con la adición de la nueva aplicación Configuración para actualizaciones del sistema operativo. Vaya a **Configuración -> Update & Security -> Troubleshoot -> Windows Update** y seleccione **Iniciar**. Esto le permite recopilar seguimientos mientras reproduce el problema con las actualizaciones del sistema operativo para ayudar a solucionar mejor los problemas con el departamento de TI o soporte técnico.
### <a name="prerequisites"></a>Requisitos previos

- La **Configuración** está instalada en el dispositivo y está disponible para el usuario.

### <a name="data-locations-access-and-retention"></a>Ubicaciones, acceso y retención de datos

Dado que el usuario inicia la recopilación de datos, el usuario da su consentimiento implícitamente al almacenamiento de la información de diagnóstico. Solo el usuario, o cualquier persona con la que el usuario comparta los datos, puede acceder a los datos.

La información de diagnóstico se almacena en el dispositivo. Si el dispositivo está conectado al equipo del usuario, la información también reside en el equipo en el archivo siguiente:

> Este archivo \\ \<*HoloLens device name*> \\ .etl Storage \\ de documentos internos del \\ \<*ddmmyyhhmmss*> equipo

> [!NOTE]  
> En esta ruta de acceso y nombre de archivo, representa el nombre del dispositivo HoloLens y representa la fecha y hora en \<*HoloLens device name*> \<*ddmmyyhhmmss*> que se creó el archivo.

La información de diagnóstico permanece en estas ubicaciones hasta que el usuario la elimina.

## <a name="diagnosticlog-csp"></a>DiagnosticLog CSP

En un entorno de Mobile Administración de dispositivos (MDM), el administrador de TI puede usar el proveedor de servicios de configuración [DiagnosticLog (CSP)](/windows/client-management/mdm/diagnosticlog-csp) para configurar las opciones de diagnóstico en los dispositivos HoloLens inscritos. El administrador de TI puede configurar estas opciones para recopilar registros de dispositivos inscritos.

Más información:
- [Recopilación de diagnósticos desde un dispositivo Windows](/mem/intune/remote-actions/collect-diagnostics)
- [Versión preliminar pública de Intune: Windows 10 diagnóstico de dispositivos](https://techcommunity.microsoft.com/t5/intune-customer-success/intune-public-preview-windows-10-device-diagnostics/ba-p/2179712#:~:text=This%20first%20release%20of%20device%20diagnostics%20utilizes%20the,taking%20about%205%20minutes%20from%20start%20to%20finish.)

### <a name="prerequisites"></a>Requisitos previos

- El dispositivo está conectado a una red.
- El dispositivo está inscrito en un entorno MDM que admite diagnosticLog CSP.

### <a name="data-locations-access-and-retention"></a>Ubicaciones de datos, acceso y retención

Dado que el dispositivo forma parte del entorno administrado, el usuario da su consentimiento implícitamente al acceso administrativo a la información de diagnóstico.

El administrador de TI usa diagnosticLog CSP para configurar las directivas de almacenamiento, retención y acceso de datos, incluidas las directivas que rigen lo siguiente:

- Infraestructura en la nube que almacena la información de diagnóstico.
- Período de retención de la información de diagnóstico.
- Permisos que controlan el acceso a la información de diagnóstico.

## <a name="offline-diagnostics"></a>Diagnósticos sin conexión
En situaciones en las que el dispositivo no puede recopilar diagnósticos a través de Centro de opiniones o el solucionador de problemas de Configuración, puede recopilar diagnósticos manualmente. Un escenario en el que esto es necesario es cuando el dispositivo no se puede conectar a Wi-Fi o no se puede acceder a otros métodos mencionados anteriormente. Los diagnósticos recopilan volcados de memoria y registros del dispositivo que ayudan a un ingeniero de soporte técnico de Microsoft a aislar los problemas.

Esto funciona cuando el dispositivo aparece en Explorador de archivos después de conectarlo a un equipo a través de un cable USB.

> [!NOTE]
> La generación y administración de diagnósticos sin conexión se controla de forma diferente en función de la versión del sistema operativo. Anteriormente se controlaba mediante la configuración de telemetría, pero ahora se controla directamente a través de la directiva MDM. Si se deshabilita mediante la configuración o la directiva MDM, los registros de diagnóstico no se pueden recopilar mediante este mecanismo.

Comportamiento anterior a [Windows Holographic, versión 20H2:](hololens-release-notes.md#windows-holographic-version-20h2)
 - El diagnóstico sin conexión solo está habilitado cuando el usuario está pasando por OOBE o el valor de directiva [System\AllowTelemetry](/windows/client-management/mdm/policy-csp-system#system-allowtelemetry) está establecido en Completo (El valor predeterminado es básico en HoloLens). 
- Para deshabilitar el diagnóstico sin conexión, vaya **a la Configuración app > Privacy** (Privacidad de la aplicación) y seleccione Basic **(Básico)** en **Diagnostic Data (Datos de diagnóstico).** En las compilaciones en las que el diagnóstico sin conexión depende de la configuración de telemetría, solo afecta a si se recopilan registros o no. No afecta a los archivos que se recopilan.
- Si el dispositivo está bloqueado, los registros no aparecerán.

En las [compilaciones Windows Holographic, versión 20H2](hololens-release-notes.md#windows-holographic-version-20h2) y versiones adelante:
- Cuando el diagnóstico de reserva está habilitado, se controlará mediante una directiva MDM específica con la configuración [correspondiente MixedReality/FallbackDiagnostics.](/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-fallbackdiagnostics)
- Si el dispositivo está bloqueado, los registros no aparecerán.

Vea este vídeo para conocer más.

> [!VIDEO https://channel9.msdn.com/Shows/Docs-Mixed-Reality/Gathering-Diagnostic-Files-on-HoloLens2/player]

Siga estos pasos para recopilar diagnósticos:
1.  Conectar el dispositivo con un cable USB al equipo.
2.  En Explorador de archivos en el equipo, vaya a **"This PC \<hololens-device> \Internal Storage" (Este equipo Storage).**
3.  Si la **carpeta Storage** interno no aparece, el dispositivo está esperando a que un usuario inicie sesión. Inicie sesión o encienda el dispositivo manteniendo presionado el botón DE ENCENDIDO durante 10 segundos.
4.  Presione y suelte inmediatamente los **botones De encendido** y bajada de volumen juntos.
5.  Espere un minuto para que el dispositivo prepare los archivos ZIP. (Un archivo temporal denominado HololensDiagnostics.temp puede ser visible mientras el dispositivo genera los archivos ZIP. No acceda a ese archivo ni guárdelo. Cuando finalice el proceso, se reemplazará por los archivos ZIP).
6.  Actualice el Explorador de archivos y vaya a la **carpeta "\Documents".**
7.  Copie los archivos ZIP de diagnóstico y compártolos con el equipo de soporte técnico de Microsoft.

> [!NOTE]
> Algunos de los archivos ZIP de diagnóstico pueden contener PII.
