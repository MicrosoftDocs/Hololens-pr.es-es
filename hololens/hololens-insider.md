---
title: Insider Preview para Microsoft HoloLens
description: Obtenga información sobre cómo empezar a trabajar con las compilaciones de Insider y proporcionar comentarios valiosos sobre nuestra próxima actualización principal del sistema operativo para HoloLens.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 09/14/2021
ms.reviewer: ''
manager: ranjibb
appliesto:
- HoloLens 2
ms.openlocfilehash: e3b067987fb339bc070fcb64ed01c28dee21ec35
ms.sourcegitcommit: 20ea1ed37772655504ccb11a7e185ed19d85f336
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2021
ms.locfileid: "127833546"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Insider Preview para Microsoft HoloLens

Le damos la bienvenida a las últimas compilaciones de Insider Preview para HoloLens. Es fácil empezar a trabajar [y proporcionar](hololens-insider.md#start-receiving-insider-builds) comentarios valiosos para nuestra próxima actualización del sistema operativo principal para HoloLens.

## <a name="windows-insider-release-notes"></a>Windows Notas de la versión de Insider

Nos complace empezar a usar nuevas características para Windows Insider. Las nuevas compilaciones se actualizarán a los canales de desarrollo y beta para las actualizaciones más recientes. Seguiremos actualizando esta página a medida que agreguemos más características y actualizaciones a nuestras compilaciones Windows Insider. Prepárese para mezclar estas actualizaciones en su realidad.

Se trata de la solución de problemas mejorada y los informes de dispositivos, algunos errores corregidos en el modo de pantalla completa y el visor de certificados, la superficie de administración ampliada y la mayor confiabilidad de las actualizaciones. Una nueva característica estrella de esta actualización de características que HoloLens es nuestro modo de plataforma móvil. Consulte todas las nuevas características excelentes para HoloLens 2.

| Característica                 | Descripción                | Usuario o escenario | Compilación introducida |
|-------------------------|----------------------------|--------------|------------------|
| [Mover el modo de plataforma](#moving-platform-mode) | Presenta la versión beta del modo de plataforma móvil, que, cuando se configura, permite el uso de HoloLens 2 en grandes navos de mar que experimentan movimiento bajo dinámico. | Todo | 20348.1411 |
| [Compatibilidad con archivos PFX para el Administrador de certificados](#pfx-file-support-for-certificate-manager) | Adición de certificados PFX a través de Configuración interfaz de usuario | Usuario final | 20348.1405 |
| [Ver el informe de diagnóstico avanzado en Configuración en HoloLens](#view-advanced-diagnostic-report-in-settings-on-hololens) | Visualización de los registros de diagnóstico de MDM en el dispositivo | Solución de problemas | 20348.1405 |
| [Notificaciones de diagnóstico sin conexión](#offline-diagnostics-notifications) | Comentarios sobre la recopilación de registros | Solución de problemas | 20348.1405 |
| [Mejoras en la recopilación de registros de almacenamiento bajo](#low-storage-log-collection-improvements) | Mejoras en los escenarios de recopilación de registros durante situaciones de almacenamiento bajo. | Solución de problemas | 20348.1412 |
| [Cambios de CSP para informes HoloLens detalles](#csp-changes-for-reporting-hololens-details) | Nuevos CSP para para consultar datos | Administradores de TI    | 20348.1403                 |
| [Directiva de inicio de sesión automático controlada por CSP](#auto-login-policy-controlled-by-csp) | Se usa para iniciar sesión automáticamente en una cuenta | Administradores de TI | 20348.1405 |
| [Notificaciones y detección de reinicio de actualizaciones mejoradas](#improved-update-restart-detection-and-notifications) | Nuevas directivas habilitadas y experiencia de usuario para actualizaciones. | Administradores de TI | 20348.1405 |
| [Reintento inteligente para actualizaciones de aplicaciones](#smart-retry-for-app-updates) | Permite a los administradores de TI programar reintentos para actualizar aplicaciones. | Administradores de TI | 20348.1405 |
| [Use solo aplicaciones de la tienda privada solo para Microsoft Store](#use-only-private-store-apps-for-microsoft-store) | Configuración de la aplicación de la tienda para mostrar solo las aplicaciones de la organización | Administración de TI | 20348.1408 |
| [Uso de aplicaciones WDAC y LOB](#use-wdac-and-lob-apps) | Permite a los administradores de TI usar sus propias aplicaciones y seguir utilizando WDAC para bloquear otras aplicaciones. | Administradores de TI | 20348.1405 |
| [Correcciones y mejoras](#fixes-and-improvements) | Correcciones y mejoras para HoloLens. | All | 20348.1411 |

### <a name="it-admin-insider-feature-checklist"></a>Lista de comprobación de características de Insider del administrador de TI

✔️ Si desea establecer una única cuenta de Azure AD para iniciar sesión automáticamente, [configure este nuevo CSP.](#auto-login-policy-controlled-by-csp) <br>
✔️ Si desea configurar las aplicaciones para que intenten actualizarse automáticamente después de no actualizar, establezca este nuevo CSP para [el reintento inteligente.](#smart-retry-for-app-updates) <br>
✔️ Si desea tener más control sobre las actualizaciones del sistema operativo, consulte estas [directivas de actualización recién habilitadas.](#improved-update-restart-detection-and-notifications) <br>
✔️ Si necesita que las aplicaciones de su organización estén disponibles en la tienda de la empresa a través de Microsoft Store, pero solo desea permitir el acceso a las aplicaciones de la organización y no a la tienda [completa,](#use-only-private-store-apps-for-microsoft-store)establezca esta directiva . <br>
✔️ Si desea conocer el espacio de almacenamiento libre, el SSID o el BSSID de los dispositivos HoloLens consulte estos [CSP](#csp-changes-for-reporting-hololens-details)de informes. <br>
✔️ Si desea usar WDAC para impedir que se inicien aplicaciones o procesos, pero también necesita usar su propia línea de aplicaciones de desuso, ahora puede permitir LOB en la directiva [WDAC](#use-wdac-and-lob-apps).

### <a name="moving-platform-mode"></a>Mover el modo de plataforma

A partir de la compilación **20348.1411 de Insider,** hemos agregado compatibilidad beta para el seguimiento en plataformas de movimiento dinámico bajo en HoloLens 2. Después de instalar la compilación y habilitar el modo de plataforma móvil, podrá usar el HoloLens 2 en entornos inaccesibles anteriormente, como grandes navos y grandes navos de gran tamaño. Actualmente, la característica está destinada a habilitar únicamente estas plataformas móviles específicas, aunque nada le impide intentar usar la característica en otros entornos. Esta característica se centra primero en agregar compatibilidad con estos entornos.

Para obtener más información sobre lo que se admite y cómo habilitar esta nueva característica, [visite la página de la plataforma móvil](hololens2-moving-platform.md).

#### <a name="overview-to-try-out-moving-platform-mode"></a>Información general para probar el modo de plataforma móvil

1. [Habilite el modo de desarrollador y el portal de dispositivos.](/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)
1. [Habilite el modo de movimiento de la plataforma a través del Portal de dispositivos.](hololens2-moving-platform.md#enabling-moving-platform-mode)
1. Lleve el dispositivo a la plataforma móvil grande y observe cómo son los hologramas estables.

### <a name="pfx-file-support-for-certificate-manager"></a>Compatibilidad con archivos PFX para el Administrador de certificados

Se introdujo en Windows Insider 20348.1405. Hemos agregado compatibilidad con el Administrador de certificados [para](certificate-manager.md) usar ahora certificados .pfx. Cuando los usuarios navegan a **Configuración** actualizar & certificados de seguridad y seleccionan Instalar un certificado, la interfaz de usuario ahora  >    >  admite el archivo de certificado .pfx. 
Los usuarios pueden importar el certificado .pfx, con clave privada, al almacén de usuarios o al almacén del equipo.

#### <a name="overview-to-try-out-pfx-files-in-certificate-manager"></a>Información general para probar archivos PFX en el Administrador de certificados

1. Prepare el archivo PFX.
1. Copie el archivo en el dispositivo a través de un cable USB-C.
1. Abra la Configuración aplicación, vaya al Administrador [de certificados](certificate-manager.md) y aplique el certificado.

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>Ver el informe de diagnóstico avanzado en Configuración en HoloLens

Para los dispositivos administrados al solucionar problemas de comportamiento, confirmar que se aplica una configuración de directiva esperada es un paso importante. Antes de esta nueva característica, la visualización de esta información tenía que realizarse fuera del dispositivo a través de MDM o cerca del dispositivo después de exportar los registros de diagnóstico de MDM recopilados a través de Configuración Accounts Access work or school (Acceso a cuentas de **Configuración** trabajo o escuela), y seleccionar Exportar los registros de administración y verlos en un equipo  ->    >  cercano. 

Ahora los diagnósticos de MDM se pueden ver en el dispositivo mediante el explorador Edge. Para ver más fácilmente el informe de diagnóstico de MDM, vaya a la página Acceso profesional o educativo y seleccione **Ver informe de diagnóstico avanzado.** Esto generará y abrirá el informe en una nueva ventana perimetral.

![Vea el informe de diagnóstico avanzado en Configuración aplicación.](./images/view-advanced-diagnostic-report.jpg)

#### <a name="overview-to-try-out-the-advanced-diagnostic-report"></a>Información general para probar el informe de diagnóstico avanzado

1. Abra la aplicación de configuración.
1. Vaya a la página Cuentas y haga clic en el nuevo vínculo **Exportar los registros de administración.**
1. Vea información avanzada sobre las configuraciones del dispositivo.

### <a name="offline-diagnostics-notifications"></a>Notificaciones de diagnóstico sin conexión

Se trata de una actualización de una característica existente denominada [Diagnósticos sin conexión.](hololens-diagnostic-logs.md#offline-diagnostics) Anteriormente, no había ningún indicador claro para los usuarios de que hubieran desencadenado la recopilación de diagnóstico o que se hubiera completado.
Ahora se han agregado Windows compilaciones de Insider, hay dos formas de comentarios sobre el diagnóstico sin conexión. El primero es notificaciones del sistema que se muestran para cuando se inicia y se completa la recopilación. Se mostrarán cuando el usuario haya iniciado sesión y tenga objetos visuales.

![Notificación del sistema para recopilar registros.](./images/logcollection1.jpg)

![Notificación del sistema cuando se completa la recopilación de registros.](./images/logcollection2.jpg)

Dado que los usuarios suelen usar diagnósticos sin conexión como mecanismo de recopilación de registros de reserva para cuando no tienen acceso a una pantalla, no pueden iniciar sesión o siguen en la OOBE, también habrá una indicación de audio reproducida cuando se recopilibrán los registros. Este sonido se reproducirá además de la notificación del sistema.

Esta nueva característica se habilitará cuando el dispositivo se actualice y no es necesario habilitarla ni administrarla. En caso de que no se puedan mostrar ni escuchar estos nuevos comentarios, se seguirá generando Diagnósticos sin conexión.

Esperamos que con esta adición más reciente de comentarios sobre el lenguaje sea más fácil recopilar datos de diagnóstico y poder solucionar los problemas más rápidamente.

#### <a name="overview-to-try-out-the-diagnostics-notifications"></a>Información general para probar las notificaciones de diagnóstico

1. Desbloquee el dispositivo y pónlo.
1. Presione la **combinación de** **botones De encendido** y Volumen para recopilar [diagnósticos sin conexión.](hololens-diagnostic-logs.md#offline-diagnostics)
1. Vea las notificaciones del sistema y escuche las indicaciones de audio de cuándo se inicia el dispositivo y finaliza la recopilación de registros.

### <a name="low-storage-log-collection-improvements"></a>Mejoras en la recopilación de registros de almacenamiento bajo

En escenarios en los que un dispositivo parece tener poco espacio en disco cuando se recopilan registros de diagnóstico, se creará un informe adicional denominado **StorageDiagnostics.zip.** El umbral de almacenamiento bajo se determina automáticamente mediante Windows [de almacenamiento.](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48)

#### <a name="overview-to-try-out-the-low-storage-improvements"></a>Información general para probar las mejoras de almacenamiento bajo

1. Rellene el espacio de almacenamiento del dispositivo.
1. Presione la **combinación de** **botones De encendido** y Volumen para recopilar [diagnósticos sin conexión.](hololens-diagnostic-logs.md#offline-diagnostics)
1. Observe que hay un nuevo archivo en la colección de registros almacenados en la carpeta Documentos de la HoloLens.

### <a name="csp-changes-for-reporting-hololens-details"></a>Cambios de CSP para informes HoloLens detalles

- Introducido en la Windows Insider, 20348.1403

Los siguientes CSP se han actualizado con nuevas formas de informar de la información de los HoloLens dispositivos.

#### <a name="devdetail-csp---free-storage"></a>CSP de DevDetail: Storage

Csp de DevDetail ahora también notifica espacio de almacenamiento libre en HoloLens dispositivo. Esto debe coincidir aproximadamente con el valor que se muestra en Configuración página de Storage aplicación. A continuación se muestra el nodo específico que contiene esta información.

- ./DevDetail/Ext/Microsoft/FreeStorage (solo operación GET)

#### <a name="devicestatus-csp---ssid-and-bssid"></a>CSP de DeviceStatus: SSID y BSSID

Csp de DeviceStatus ahora también notifica SSID y BSSID de Wi-Fi red con la HoloLens está conectada activamente. A continuación se incluyen los nodos específicos que contienen esta información.

- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*dirección mac del Wi-Fi /SSID*
- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/ dirección mac del *Wi-Fi /BSSID*

Blob syncml de ejemplo (para proveedores de MDM) para consultar NetworkIdentifiers

```xml
<SyncML>
<SyncBody>
    <Get>
        <CmdID>$CmdID$</CmdID>
        <Item>
            <Target>
            <LocURI>
                ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers?list=StructData
            </LocURI>
            </Target>
        </Item>
    </Get>
    <Final/>
</SyncBody>
</SyncML>
```

### <a name="auto-login-policy-controlled-by-csp"></a>Directiva de inicio de sesión automático controlada por CSP

Esta nueva directiva AutoLogonUser controla si un usuario iniciará sesión automáticamente. Algunos clientes quieren configurar dispositivos que están vinculados a una identidad, pero no quieren ninguna experiencia de inicio de sesión. Imagine seleccionar un dispositivo y usar asistencia remota inmediatamente. O bien, tener la ventaja de poder distribuir rápidamente HoloLens dispositivos y permitir a los usuarios finales acelerar el inicio de sesión.

Cuando la directiva se establece en un valor no vacío, especifica la dirección de correo electrónico del usuario de inicio de sesión automático. El usuario especificado debe iniciar sesión en el dispositivo al menos una vez para habilitar el inicio de sesión automático.

OMA-URI del nuevo valor de cadena `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` de directiva

- El usuario con la misma dirección de correo electrónico tendrá habilitado el inicio de sesión automático.

En un dispositivo donde se configura esta directiva, el usuario especificado en la directiva tendrá que iniciar sesión al menos una vez. Los reinicios posteriores del dispositivo después del primer inicio de sesión harán que el usuario especificado inicie sesión automáticamente. Solo se admite un único usuario de inicio de sesión automático. Una vez habilitado, el usuario que ha iniciado sesión automáticamente no podrá cerrar sesión manualmente. Para iniciar sesión como un usuario diferente, primero se debe deshabilitar la directiva.

> [!NOTE]
>
> - Algunos eventos, como las actualizaciones principales del sistema operativo, pueden requerir que el usuario especificado vuelva a iniciar sesión en el dispositivo para reanudar el comportamiento de inicio de sesión automático.
> - El inicio de sesión automático solo se admite para los usuarios de MSA y AAD.

#### <a name="overview-to-try-auto-logon-csp"></a>Información general para probar el CSP de inicio de sesión automático

1. Configure el nuevo CSP para un usuario deseado [mediante una directiva personalizada:](/mem/intune/configuration/custom-settings-windows-10)`./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser`
1. Aplique el CSP al dispositivo mediante el paquete [de aprovisionamiento o](hololens-provisioning.md) [MDM](hololens-mdm-configure.md).
1. Inicie sesión en la cuenta especificada.
1. Reinicie el dispositivo y observe que el usuario ha iniciado sesión automáticamente.

### <a name="improved-update-restart-detection-and-notifications"></a>Notificaciones y detección de reinicio de actualizaciones mejoradas

Entre las horas activas y las directivas de tiempo de instalación, es posible evitar reiniciar HoloLens dispositivos cuando están en uso. Sin embargo, también retrasaría la adopción de actualizaciones si no se producen reinicios para completar la instalación de una actualización necesaria. Ahora se han agregado directivas para permitir que EL EQUIPO de INFORMACIÓN aplique las fechas límite y los reinicios necesarios y asegúrese de que la instalación de una actualización se complete de forma oportuna. Los usuarios pueden recibir una notificación antes de iniciar el reinicio y pueden retrasar el reinicio de acuerdo con la directiva de IT.

Se agregaron las siguientes directivas de actualización:

- [Update/AutoRestartNotificationSchedule](/windows/client-management/mdm/policy-csp-update#update-autorestartnotificationschedule)
- [Update/AutoRestartRequiredNotificationDismissal](/windows/client-management/mdm/policy-csp-update#update-autorestartrequirednotificationdismissal)
- [Update/ConfigureDeadlineForFeatureUpdates](/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforfeatureupdates)
- [Update/ConfigureDeadlineForQualityUpdates](/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforqualityupdates)
- [Update/ConfigureDeadlineGracePeriod](/windows/client-management/mdm/policy-csp-update#update-configuredeadlinegraceperiod)
- [Update/ConfigureDeadlineNoAutoReboot](/windows/client-management/mdm/policy-csp-update#update-configuredeadlinenoautoreboot)
- [Update/ScheduleImminentRestartWarning](/windows/client-management/mdm/policy-csp-update#update-scheduleimminentrestartwarning)
- [Update/ScheduleRestartWarning](/windows/client-management/mdm/policy-csp-update#update-schedulerestartwarning)
- [Update/UpdateNotificationLevel](/windows/client-management/mdm/policy-csp-update#update-updatenotificationlevel)

#### <a name="overview-to-try-new-update-notifications"></a>Información general para probar nuevas notificaciones de actualización

1. Configure uno de los NUEVOS CSP de actualización mediante el paquete [de aprovisionamiento](hololens-provisioning.md) o [MDM](hololens-mdm-configure.md) (consulte la lista de vínculos anterior y elija una).
1. Use el dispositivo durante la hora programada.
1. Observe que se notifica al usuario sobre la actualización y la necesidad de reiniciar el \* dispositivo.

\* Los resultados pueden variar en función de las directivas de actualización usadas.

### <a name="smart-retry-for-app-updates"></a>Reintento inteligente para actualizaciones de aplicaciones

Ahora habilitado para HoloLens es una nueva directiva que permite a los administradores de TI establecer una fecha periódica o una hora para reiniciar las aplicaciones cuya actualización no se pudo realizar debido a que la aplicación está en uso, lo que permite aplicar la actualización. Estos se pueden establecer en función de algunos desencadenadores diferentes, como una hora programada o el inicio de sesión. Para obtener más información sobre cómo usar esta vista de directiva [ApplicationManagement/ScheduleForceRestartForUpdateFailures](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures).

#### <a name="overview-to-try-smart-retry-for-app-updates"></a>Información general para probar el reintento inteligente para las actualizaciones de aplicaciones

1. Configure la nueva característica de reintento inteligente.
1. En un dispositivo que aún no ha recibido la aplicación y está configurado correctamente, inicie sesión en un entorno en línea.
1. Hacer que el dispositivo no pueda descargar la aplicación por medio de desactivarla o desconectarla.
1. Haga que el dispositivo esté encendido y conectado a Internet durante el tiempo desencadenado para reintentar la descarga.

### <a name="use-only-private-store-apps-for-microsoft-store"></a>Usar solo aplicaciones de la tienda privada para Microsoft Store

La directiva RequirePrivateStoreOnly se ha habilitado para HoloLens. Esta directiva permite configurar Microsoft Store aplicación para mostrar solo el almacén privado configurado para su organización. Limitar el acceso solo a las aplicaciones que ha puesto a disposición.

Obtenga más información [sobre ApplicationManagement/RequirePrivateStoreOnly.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

#### <a name="overview-to-try-only-private-store-apps"></a>Información general para probar solo aplicaciones de la tienda privada

1. Configure la nueva directiva para los dispositivos a través de [MDM.](hololens-mdm-configure.md)
1. Inicie sesión en un dispositivo que tenga la directiva.
1. Abra la Microsoft Store aplicación y observe que solo puede ver las aplicaciones de su organización.

### <a name="use-wdac-and-lob-apps"></a>Uso de aplicaciones WDAC y LOB

Ahora puede usar WDAC para impedir que las aplicaciones o los procesos se inicien y seguir usando su propia línea de aplicaciones de desuso. ahora puede permitirlas en la directiva WDAC. El uso de esta directiva implica la ejecución de una línea de código adicional en PowerShell al crear la directiva WDAC. [Revise los pasos que se indican aquí.](/mem/intune/configuration/custom-profile-hololens)

#### <a name="overview-to-try-your-own-apps-while-using-wdac-to-block-others"></a>Información general para probar sus propias aplicaciones mientras se usa WDAC para bloquear otras

1. Recopila los AUMID de la aplicación LOB y las aplicaciones que quiere bloquear.
1. [Cree una nueva directiva WDAC siguiendo](/mem/intune/configuration/custom-profile-hololens) los nuevos pasos.
1. [Implemente la directiva mediante MDM](hololens-mdm-configure.md) en el dispositivo.
1. Inicie sesión en el dispositivo y observe que puede iniciar la aplicación y bloquear otras.

### <a name="fixes-and-improvements"></a>Correcciones y mejoras

- Se ha [corregido un problema conocido Portal de dispositivos donde no había ningún mensaje que descargara archivos bloqueados.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- Se ha corregido un problema conocido para Portal de dispositivos con los tiempos de espera de [carga y descarga de archivos.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)
- Aborda los problemas relacionados con las propiedades de cumplimiento de informes de HoloLens dispositivos. Es posible que sea necesario reiniciar para que se desencadene la generación de informes correcta en las compilaciones de Insider.  
- Se ha [habilitado una API de](/uwp/api/windows.system.userprofile.assignedaccesssettings?view=winrt-20348&preserve-view=true) acceso asignado para que las aplicaciones puedan determinar ahora si un HoloLens se está ejecutando en un modo de pantalla completa para el usuario que ha iniciado sesión en el HoloLens.
- Se ha actualizado la versión de Remote Assist que se instala en flashes nuevos.
- El procesamiento de gamepad para aplicaciones 2D se deshabilitó en las compilaciones de Insider. Al quitarlo, las aplicaciones ahora pueden usar las API de Gamepad directamente y tener acceso a todo el conjunto de controles y hacer lo que quieran. Los desarrolladores deben usar las API de Gamepad para consumir la entrada de Gamepad. Este es un ejemplo de [la clase Gamepad (Windows. Gaming.Input): Windows aplicaciones para UWP.](/uwp/api/windows.gaming.input.gamepad?view=winrt-20348&preserve-view=true)
- Se ha corregido un problema por el que, después del primer inicio de sesión de usuario, se finalizaba OOBE en escenarios en los que se usaban configuraciones de pantalla completa basadas en grupos de AAD.
- Se ha corregido un problema en torno a la visualización de notificaciones de actualización y mensajes de diálogo para reiniciar el dispositivo.

## <a name="start-receiving-insider-builds"></a>Empezar a recibir compilaciones de Insider

> [!NOTE]
> Si no se ha actualizado recientemente, reinicie el dispositivo para actualizar el estado y obtener la compilación más reciente.
>
> - El comando de voz "Reiniciar dispositivo" funciona bien.
> - También puede elegir el botón reiniciar en Configuración/Windows Programa Insider.
>
> Hemos tenido un error en el back-end que es posible que haya encontrado y esto le permitirá volver a realizar el seguimiento.

En un HoloLens 2, vaya **a Configuración** Update & Security Windows Programa Insider y  >    >   seleccione **Introducción.** Vincule la cuenta que usó para registrarse como Windows Insider.

> [!NOTE]
> Para inscribir el dispositivo en compilaciones de Insider, deberá habilitar la telemetría opcional. Si aún no lo ha hecho, abra la aplicación Configuración, seleccione Privacy Diagnostics & feedback (Diagnósticos de privacidad) y, a continuación, seleccione Optional diagnostics data (Datos  ->   de **diagnóstico opcionales).**

Windows insider se está moviendo a Canales. El **anillo** rápido se convertirá en  el canal **de desarrollo,** el  anillo lento se convertirá en el **Canal beta** y el anillo versión preliminar se convertirá en el canal de versión preliminar de la **versión .** Este es el aspecto de esa asignación:

![Windows Explicación de los canales de Insider.](images/WindowsInsiderChannels.png)

Para obtener más información, [vea Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) en Windows Blogs.
A continuación, seleccione Desarrollo **activo de Windows**, elija si desea recibir el canal **de** desarrollo o Canal beta **compilaciones** y revise los términos del programa.
Seleccione **Confirmar > Reiniciar ahora** para finalizar. Una vez reiniciado el dispositivo, vaya a Configuración > **Update & Security > Buscar** actualizaciones para obtener la compilación más reciente.

### <a name="update-error-0x80070490-work-around"></a>Actualización de la 0x80070490 de errores

Si se produce un error de actualización 0x80070490 al actualizar en el canal Dev o Beta, pruebe el siguiente trabajo a corto plazo. Implica mover el canal insider, seleccionar la actualización y, a continuación, volver a mover el canal insider.

#### <a name="stage-one---release-preview"></a>Fase uno: versión preliminar

1. Configuración, Update & Security, Windows Programa Insider, seleccione Release **Preview Channel (Canal de versión preliminar de versión preliminar).**

2. Configuración, Update & Security, Windows Update, **Check for updates**. Después de la actualización, continúe con la fase dos.

#### <a name="stage-two---dev-channel"></a>Fase dos: Canal de desarrollo

1. Configuración, Actualizar & seguridad, Windows Programa Insider, seleccione **Canal de desarrollo.**

2. Configuración, Update & Security, Windows Update, **Check for updates**.

## <a name="ffu-download-and-flash-directions"></a>Instrucciones de descarga y flash de FFU

Para probar con un vuelo firmado con ffu, primero debe desbloquear el dispositivo antes de parpadear el vuelo firmado ffu.

1. En pc:
    1. Descargue ffu en el equipo desde [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .

    1. Instale ARC (Advanced Recovery Companion) desde la Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .

1. En HoloLens- Desbloqueo de vuelo: abra **Configuración**  >  **Update & Security** Windows Programa Insider y, a continuación, regístrese y reinicie el  >   dispositivo.

1. Flash FFU: ahora puede flashear el vuelo firmado con FFU mediante ARC.

### <a name="provide-feedback-and-report-issues"></a>Proporcionar comentarios e informar de problemas

Use la [aplicación Centro de opiniones en](hololens-feedback.md) su cuenta HoloLens para proporcionar comentarios e informar sobre los problemas. El Centro de opiniones garantiza que se incluye toda la información de diagnóstico necesaria para ayudar a nuestros ingenieros a depurar y resolver rápidamente el problema.  Los problemas con la versión en chino y japonés HoloLens deben informarse de la misma manera.

> [!NOTE]
> Asegúrese de aceptar el mensaje que le pregunta si desea Centro de opiniones acceso a la carpeta Documentos **(seleccione Sí cuando** se le solicite).

## <a name="note-for-developers"></a>Nota para desarrolladores

Le recomendamos que pruebe a desarrollar sus aplicaciones mediante las compilaciones insider de HoloLens.  Consulte la documentación [HoloLens developer para](https://developer.microsoft.com/windows/mixed-reality/development) empezar. Esas mismas instrucciones funcionan con compilaciones de Insider de HoloLens.  Puede usar las mismas compilaciones de Unity y Visual Studio que ya usa para el HoloLens desarrollo.

## <a name="stop-receiving-insider-builds"></a>Dejar de recibir compilaciones de Insider

Si ya no quiere recibir compilaciones de Insider de Windows Holographic, puede optar por no recibir cuando [](hololens-recovery.md) el HoloLens ejecuta una compilación de producción o puede recuperar el dispositivo mediante advanced recovery Companion para recuperar el dispositivo en una versión que no sea insider de Windows Holographic.

> [!CAUTION]
> Hay un problema conocido en el que los usuarios que no se inscriban en las compilaciones de Insider Preview después de volver a instalar manualmente una nueva compilación de versión preliminar experimentarían una pantalla azul. Después, deben recuperar manualmente su dispositivo. Para obtener información completa sobre si se vería afectado o no, consulte más información sobre [este problema conocido.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)

Para comprobar que el HoloLens está ejecutando una compilación de producción:

1. Vaya a **Configuración > System > Acerca de** y busque el número de compilación.

1. [Consulte las notas de la versión de los números de compilación de producción.](hololens-release-notes.md)

Para no participar en las compilaciones de Insider:

1. En un HoloLens una compilación de producción, vaya a **Configuración > Update & Security > Windows Programa Insider** y seleccione Detener **compilaciones de Insider.**

1. Siga las instrucciones para no participar en el dispositivo.
