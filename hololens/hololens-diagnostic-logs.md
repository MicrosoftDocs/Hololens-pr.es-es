---
title: Recopilación y uso de la información de diagnóstico de dispositivos HoloLens
description: Obtenga información sobre cómo recopilar, usar y conservar información de diagnóstico de HoloLens dispositivos.
author: Teresa-Motiv
ms.author: v-tea
ms.date: 9/12/2021
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
ms.openlocfilehash: 4f62a70430d78087157b3adcdf76af53183db708
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924403"
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
> **Usuarios comerciales o empresariales:** Si usa la aplicación Centro de opiniones para notificar un problema relacionado con MDM, el aprovisionamiento o cualquier otro aspecto de administración de dispositivos, cambie la categoría de la aplicación a **Enterprise categoría** Dispositivo de  >  **administración**.

>[!IMPORTANT]
> Para proporcionar los mejores datos posibles para corregir problemas, se recomienda encarecidamente establecer la telemetría del dispositivo en **Opcional.** Puede establecer este valor durante la configuración rápida (OOBE) o mediante la **aplicación Configuración** configuración. Para ello mediante el uso de Configuración, seleccione **Start > Configuración > Privacy > App Diagnostics > On**(Iniciar > Configuración > diagnósticos de > aplicación en ).

### <a name="prerequisites"></a>Requisitos previos

- El dispositivo está conectado a una red.
- La Centro de opiniones está disponible en el equipo de escritorio del usuario y el usuario puede cargar archivos en la nube de Microsoft.

### <a name="data-locations-access-and-retention"></a>Ubicaciones de datos, acceso y retención

Al aceptar los términos de uso del Centro de opiniones, el usuario da su consentimiento explícitamente para el almacenamiento y el uso de los datos (tal como se define en ese contrato).

El Centro de opiniones proporciona dos lugares para que el usuario almacene información de diagnóstico:

- **La nube de Microsoft**. Los datos que el usuario carga mediante la aplicación Centro de opiniones se almacenan durante el número de días que es coherente con los requisitos de privacidad de próxima generación (NGP). Los empleados de Microsoft pueden usar un visor compatible con NGP para acceder a la información durante este período.

   > [!NOTE]  
   > Estos requisitos se aplican a los datos de todas Centro de opiniones categorías.

- **El HoloLens .** Al presentar un informe en Centro de opiniones, el usuario puede seleccionar Guardar una copia local de diagnósticos y datos **adjuntos creados al proporcionar comentarios**. Si el usuario selecciona esta opción, el Centro de opiniones almacena una copia de la información de diagnóstico en el HoloLens dispositivo. Esta información sigue siendo accesible para el usuario (o cualquier persona que use esa cuenta para iniciar sesión en HoloLens). Para eliminar esta información, un usuario debe tener permisos **de** propietario del dispositivo **o** administrador en el dispositivo. Un usuario que tenga los permisos adecuados puede iniciar sesión en el Centro de opiniones, seleccionar Configuración Ver registros de diagnóstico y  >  eliminar la información.

## <a name="settings-troubleshooter"></a>Configuración Solucionador

Un HoloLens usuario puede usar la aplicación **Configuración** en el dispositivo para solucionar problemas y recopilar información de diagnóstico. Para ello, realice los pasos siguientes:

1. Abra la aplicación Configuración y seleccione Actualizar & **solución de problemas**  >  **de** seguridad.
1. Seleccione el área adecuada y seleccione **Iniciar.**
1. Reproduzca el problema.
1. Después de reproducir el problema, vuelva a Configuración seleccione **Detener**.

Un usuario también puede configurar el comportamiento de los diagnósticos de reserva desde la **Configuración** aplicación. Vaya a **la página privacidad -> solución de problemas** para configurar esta opción.
> [!NOTE]
> Si hay una directiva MDM configurada para el dispositivo, el usuario no podrá invalidar ese comportamiento.

### <a name="os-update-troubleshooter"></a>Solucionador de problemas de actualización del sistema operativo

En las [compilaciones Windows Holographic, versión 21H1](hololens-release-notes.md#windows-holographic-version-21h1) y versiones adelante:
- Además de los solucionadores de problemas anteriores dentro de la aplicación Configuración, se ha agregado un nuevo solucionador de problemas con la adición de la nueva aplicación Configuración para las actualizaciones del sistema operativo. Vaya a **Configuración -> Update & Security -> Troubleshoot -> Windows Update** y seleccione **Iniciar**. Esto le permite recopilar seguimientos mientras reproduce el problema con las actualizaciones del sistema operativo para ayudar a solucionar mejor problemas con el equipo de TI o el soporte técnico.

### <a name="prerequisites"></a>Requisitos previos

- La **Configuración** está instalada en el dispositivo y está disponible para el usuario.

### <a name="data-locations-access-and-retention"></a>Ubicaciones de datos, acceso y retención

Dado que el usuario inicia la recopilación de datos, el usuario da su consentimiento implícitamente al almacenamiento de la información de diagnóstico. Solo el usuario, o cualquier persona con la que el usuario comparta los datos, puede acceder a los datos.

La información de diagnóstico se almacena en el dispositivo. Si el dispositivo está conectado al equipo del usuario, la información también reside en el equipo en el archivo siguiente:

> Este archivo \\ \<*HoloLens device name*> \\ .etl Storage \\ de documentos internos del \\ \<*ddmmyyhhmmss*> equipo

> [!NOTE]  
> En esta ruta de acceso y nombre de archivo, representa el nombre del dispositivo HoloLens y representa la fecha y hora \<*HoloLens device name*> \<*ddmmyyhhmmss*> en que se creó el archivo.

La información de diagnóstico permanece en estas ubicaciones hasta que el usuario la elimina.

### <a name="view-diagnostic-report"></a>Vista del informe de diagnóstico

Para ver los diagnósticos de MDM en HoloLens 2, seleccione el icono de Wi-Fi y, a continuación, vaya **a Configuración** Accounts Access work or school (Acceso a cuentas de Configuración acceso a trabajo o escuela) y seleccione Export your management logs (Exportar los registros de  ->    >   **administración).** HoloLens los archivos de registro a su cuenta y muestra su ubicación en el equipo de escritorio.

## <a name="diagnosticlog-csp"></a>DiagnosticLog CSP

En un entorno de Administración de dispositivos móvil (MDM), el administrador de TI puede usar el proveedor de servicios de configuración [diagnosticLog (CSP)](/windows/client-management/mdm/diagnosticlog-csp) para configurar los valores de diagnóstico en los dispositivos HoloLens inscritos. El administrador de TI puede configurar estas opciones para recopilar registros de dispositivos inscritos.

Más información:
- [Recopilación de diagnósticos desde un dispositivo Windows](/mem/intune/remote-actions/collect-diagnostics)
- [Versión preliminar pública de Intune: Windows 10 de dispositivos](https://techcommunity.microsoft.com/t5/intune-customer-success/intune-public-preview-windows-10-device-diagnostics/ba-p/2179712#:~:text=This%20first%20release%20of%20device%20diagnostics%20utilizes%20the,taking%20about%205%20minutes%20from%20start%20to%20finish.)

### <a name="prerequisites"></a>Requisitos previos

- El dispositivo está conectado a una red.
- El dispositivo está inscrito en un entorno MDM que admite diagnosticLog CSP.

### <a name="data-locations-access-and-retention"></a>Ubicaciones de datos, acceso y retención

Dado que el dispositivo forma parte del entorno administrado, el usuario da su consentimiento implícitamente al acceso administrativo a la información de diagnóstico.

El administrador de TI usa diagnosticLog CSP para configurar las directivas de almacenamiento, retención y acceso de datos, incluidas las directivas que rigen lo siguiente:

- La infraestructura en la nube que almacena la información de diagnóstico.
- Período de retención de la información de diagnóstico.
- Permisos que controlan el acceso a la información de diagnóstico.

## <a name="offline-diagnostics"></a>Diagnósticos sin conexión

En situaciones en las que el dispositivo no puede recopilar diagnósticos mediante Centro de opiniones o el solucionador de problemas de Configuración, puede recopilar diagnósticos manualmente. Un escenario en el que esto es necesario es cuando el dispositivo no se puede conectar a Wi-Fi o no se puede acceder a otros métodos mencionados anteriormente. Los diagnósticos recopilan volcados de memoria y registros del dispositivo que ayudan a un ingeniero de soporte técnico de Microsoft a aislar los problemas.

Esto funciona cuando el dispositivo aparece en Explorador de archivos después de conectarlo a un equipo a través de un cable USB.

> [!NOTE]
> La generación y administración de diagnósticos sin conexión se controla de forma diferente en función de la versión del sistema operativo. Anteriormente se controlaba mediante la configuración de telemetría, pero ahora se controla directamente a través de la directiva MDM. Si se deshabilita mediante la configuración o la directiva MDM, los registros de diagnóstico no se pueden recopilar mediante este mecanismo.

Comportamiento anterior a [Windows Holographic, versión 20H2:](hololens-release-notes.md#windows-holographic-version-20h2)
 - El diagnóstico sin conexión solo se habilita cuando el usuario pasa por OOBE o el valor de la directiva [System\AllowTelemetry](/windows/client-management/mdm/policy-csp-system#system-allowtelemetry) está establecido en Completo (Básico es el valor predeterminado en HoloLens). 
- Para deshabilitar el diagnóstico sin conexión, vaya a la Configuración App > Privacy (Privacidad de App **>)** y **seleccione Basic (Básico) en** Datos de **diagnóstico.** En las compilaciones en las que el diagnóstico sin conexión depende de la configuración de telemetría, solo afecta a si se recopilan registros o no. No afecta a los archivos que se recopilan.
- Si el dispositivo está bloqueado, los registros no aparecerán.

En las [compilaciones Windows Holographic, versión 20H2](hololens-release-notes.md#windows-holographic-version-20h2) y versiones adelante:
- Cuando el diagnóstico de reserva está habilitado, se controlará mediante una directiva MDM específica con la configuración [correspondiente MixedReality/FallbackDiagnostics.](/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-fallbackdiagnostics)
- Si el dispositivo está bloqueado, los registros no aparecerán.

Vea este vídeo para conocer más.

> [!VIDEO https://channel9.msdn.com/Shows/Docs-Mixed-Reality/Gathering-Diagnostic-Files-on-HoloLens2/player]

Siga estos pasos para recopilar diagnósticos:

1.  Conectar el dispositivo con un cable USB al equipo.

2.  En Explorador de archivos en el equipo, vaya a **"This PC \<hololens-device> \Internal Storage".**

3.  Si la **carpeta Storage** interna no aparece, el dispositivo está esperando a que un usuario inicie sesión. Inicie sesión o encienda el dispositivo manteniendo presionado el botón DE ENCENDIDO durante 10 segundos.

4.  Presione y suelte inmediatamente los botones **De encendido y volumen** abajo juntos.

5.  Espere un minuto para que el dispositivo prepare los archivos ZIP. (Un archivo temporal denominado HololensDiagnostics.temp puede ser visible mientras el dispositivo genera los archivos ZIP. No acceda a ese archivo ni guárdelo. Cuando finalice el proceso, se reemplazará por los archivos ZIP).

6.  Actualice el Explorador de archivos y vaya a la **carpeta "\Documents".**

7.  Copie los archivos ZIP de diagnóstico y compártolos con el equipo de soporte técnico de Microsoft.

> [!NOTE]
> Algunos de los archivos ZIP de diagnóstico pueden contener PII.

### <a name="offline-diagnostics-notifications"></a>Notificaciones de diagnóstico sin conexión

- Introducido en [Windows Holographic, versión 21H2.](hololens-release-notes.md#windows-holographic-version-21h2)

Se trata de una actualización de una característica existente denominada [Diagnósticos sin conexión.](hololens-diagnostic-logs.md#offline-diagnostics) Anteriormente, no había ningún indicador claro para los usuarios de que hubieran desencadenado la recopilación de diagnóstico o que se hubiera completado.
Ahora se han agregado Windows compilaciones de Insider, hay dos formas de comentarios sobre el lenguaje para el diagnóstico sin conexión. El primero es notificaciones del sistema que se muestran para cuando se inicia y se completa la recopilación. Se mostrarán cuando el usuario haya iniciado sesión y tenga objetos visuales.

![Notificación del sistema para recopilar registros.](./images/logcollection1.jpg)

![Notificación del sistema cuando se completa la recopilación de registros.](./images/logcollection2.jpg)

Dado que los usuarios suelen usar diagnósticos sin conexión como mecanismo de recopilación de registros de reserva para cuando no tienen acceso a una pantalla, no pueden iniciar sesión o siguen en la OOBE, también habrá una indicación de audio reproducida cuando se recopilibrán los registros. Este sonido se reproducirá además de la notificación del sistema.

Esta nueva característica se habilitará cuando el dispositivo se actualice y no es necesario habilitarla ni administrarla. En caso de que no se puedan mostrar ni escuchar estos nuevos comentarios, se seguirá generando Diagnósticos sin conexión.

Esperamos que con esta adición más reciente de comentarios sobre el lenguaje sea más fácil recopilar datos de diagnóstico y poder solucionar los problemas más rápidamente.

### <a name="low-storage-log-collection-improvements"></a>Mejoras en la recopilación de registros de almacenamiento bajo

- Introducido en [Windows Holographic, versión 21H2.](hololens-release-notes.md#windows-holographic-version-21h2)

En escenarios en los que un dispositivo parece tener poco espacio  en disco cuando se recopilan registros de diagnóstico, se creará un informe adicionalStorageDiagnostics.zip. El umbral de almacenamiento bajo se determina automáticamente mediante Windows [de almacenamiento.](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48)

## <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>Ver el informe de diagnóstico avanzado en Configuración en HoloLens

- Introducido en [Windows Holographic, versión 21H2.](hololens-release-notes.md#windows-holographic-version-21h2)

Para los dispositivos administrados al solucionar problemas de comportamiento, confirmar que se aplica una configuración de directiva esperada es un paso importante. Antes de esta nueva característica, esto se tenía que hacer fuera del dispositivo a través de MDM o cerca del dispositivo después de exportar los registros de diagnóstico de MDM recopilados a través de Configuración Accounts Access work or school (Acceso a cuentas de **Configuración** trabajo o escuela), y seleccionar Exportar los registros de administración y verlos en un equipo  ->    >  cercano. 

Ahora los diagnósticos de MDM se pueden ver en el dispositivo mediante el explorador Edge. Para ver más fácilmente el informe de diagnóstico de MDM, vaya a la página Acceso profesional o educativo y seleccione **Ver informe de diagnóstico avanzado.** Esto generará y abrirá el informe en una nueva ventana perimetral.

![Vea el informe de diagnóstico avanzado en Configuración aplicación.](./images/view-advanced-diagnostic-report.jpg)
