---
title: Insider Preview para Microsoft HoloLens
description: Obtenga información sobre cómo empezar a trabajar con compilaciones de Insider y proporcionar comentarios valiosos para nuestra próxima actualización de sistema operativo principal para HoloLens.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: e8adb2f796299c99a9152a5b245e8bdd0b768f05
ms.sourcegitcommit: 78e5f26014e55c13fee9c2b75a80810fd2e77877
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/31/2021
ms.locfileid: "115009347"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Insider Preview para Microsoft HoloLens

Le damos la bienvenida a las últimas compilaciones de Insider Preview para HoloLens. Es fácil empezar a trabajar [y proporcionar](hololens-insider.md#start-receiving-insider-builds) comentarios valiosos para nuestra próxima actualización importante del sistema operativo para HoloLens.

## <a name="windows-insider-release-notes"></a>Windows Notas de la versión de Insider

Nos complace empezar a usar nuevas características para Windows Insiders. Las nuevas compilaciones pasarán a los canales de desarrollo y beta para las actualizaciones más recientes. Seguiremos actualizando esta página a medida que agreguemos más características y actualizaciones a nuestras compilaciones Windows Insider. Prepárese para mezclar estas actualizaciones en su realidad.

| Característica                 | Descripción                | Usuario o escenario | Compilación introducida |
|-------------------------|----------------------------|--------------|------------------|
| [Cambios de CSP para los informes HoloLens detalles](#csp-changes-for-reporting-hololens-details) | Nuevos CSP para para consultar datos | Administradores de TI    | 20348.1403                 |
| [Directiva de inicio de sesión automático controlada por CSP](#auto-login-policy-controlled-by-csp) | Se usa para iniciar sesión automáticamente en una cuenta | Administradores de TI | 20348.1405 |
| [Compatibilidad con archivos PFX para el Administrador de certificados](#pfx-file-support-for-certificate-manager) | Adición de certificados PFX a través de Configuración interfaz de usuario | Usuario final | 20348.1405 |
| [Ver el informe de diagnóstico avanzado en Configuración en HoloLens](#view-advanced-diagnostic-report-in-settings-on-hololens) | Visualización de registros de diagnóstico de MDM en el dispositivo | Solución de problemas | 20348.1405 |
| [Notificaciones de diagnóstico sin conexión](#offline-diagnostics-notifications) | Comentarios de reos para la recopilación de registros | Solución de problemas | 20348.1405 |
| [Use solo aplicaciones de la tienda privada solo para Microsoft Store](#use-only-private-store-apps-for-microsoft-store) | Configuración de la aplicación de la tienda para mostrar solo las aplicaciones de la organización | Administración de TI | 20348.1408 |
| [Mejoras en la recopilación de registros de almacenamiento bajo](#low-storage-log-collection-improvements) | Mejoras en los escenarios de recopilación de registros en situaciones de almacenamiento bajo. | Administración de TI | 20348.1412 |
| [Correcciones y mejoras](hololens-insider.md#fixes-and-improvements) | Correcciones y mejoras para HoloLens. | Todo | 20348.1411 |

### <a name="csp-changes-for-reporting-hololens-details"></a>Cambios de CSP para informes HoloLens detalles

- Introducido en la Windows Insider, 20348.1403

Los siguientes CSP se han actualizado con nuevas formas de informar de la información de los HoloLens dispositivos.

#### <a name="devdetail-csp---free-storage"></a>CSP de DevDetail: Storage

Csp de DevDetail ahora también notifica espacio de almacenamiento libre en HoloLens dispositivo. Debe coincidir aproximadamente con el valor que se muestra en Configuración página de Storage aplicación. A continuación se muestra el nodo específico que contiene esta información.

- ./DevDetail/Ext/Microsoft/FreeStorage (solo operación GET)

#### <a name="devicestatus-csp---ssid-and-bssid"></a>CSP de DeviceStatus: SSID y BSSID

Csp de DeviceStatus ahora también notifica SSID y BSSID de Wi-Fi red con la HoloLens está conectada activamente. A continuación se incluyen los nodos específicos que contienen esta información.

- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*dirección mac del Wi-Fi /SSID*
- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*dirección mac de Wi-Fi adaptador*/BSSID

Ejemplo de blob syncml (para proveedores de MDM) para consultar NetworkIdentifiers

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

Esta nueva directiva AutoLogonUser controla si un usuario iniciará sesión automáticamente. Algunos clientes quieren configurar dispositivos que están vinculados a una identidad, pero no quieren ninguna experiencia de inicio de sesión. Imagine seleccionar un dispositivo y usar asistencia remota inmediatamente. O bien, tener la ventaja de poder distribuir rápidamente HoloLens dispositivos y permitir a sus usuarios finales acelerar el inicio de sesión.

Cuando la directiva se establece en un valor no vacío, especifica la dirección de correo electrónico del usuario de inicio de sesión automático. El usuario especificado debe iniciar sesión en el dispositivo al menos una vez para habilitar el inicio de sesión automático.

El OMA-URI del nuevo valor de `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` cadena de directiva

- El usuario con la misma dirección de correo electrónico tendrá habilitado el inicio de sesión automático.

En un dispositivo donde se configura esta directiva, el usuario especificado en la directiva tendrá que iniciar sesión al menos una vez. Los reinicios posteriores del dispositivo después del primer inicio de sesión harán que el usuario especificado inicie sesión automáticamente. Solo se admite un usuario de inicio de sesión automático. Una vez habilitado, el usuario que ha iniciado sesión automáticamente no podrá cerrar sesión manualmente. Para iniciar sesión como un usuario diferente, la directiva debe deshabilitarse primero.

> [!NOTE]
> - Algunos eventos, como las actualizaciones principales del sistema operativo, pueden requerir que el usuario especificado vuelva a iniciar sesión en el dispositivo para reanudar el comportamiento de inicio de sesión automático. 
> - El inicio de sesión automático solo es compatible con usuarios de MSA y AAD.

### <a name="pfx-file-support-for-certificate-manager"></a>Compatibilidad con archivos PFX para el Administrador de certificados

Se introdujo en Windows Insider 20348.1405. Hemos agregado compatibilidad con el Administrador [de](certificate-manager.md) certificados para usar ahora certificados .pfx. Cuando los usuarios navegan a **Configuración** actualizar & certificados de seguridad y seleccionan Instalar un certificado, la interfaz de usuario ahora admite el archivo de certificado  >    >  .pfx. 
Los usuarios pueden importar el certificado .pfx, con clave privada, al almacén de usuarios o al almacén de máquinas.

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>Ver el informe de diagnóstico avanzado en Configuración en HoloLens

En el caso de los dispositivos administrados al solucionar problemas de comportamiento, confirmar que se aplica una configuración de directiva esperada es un paso importante. Antes de esta nueva característica, esto se tenía que hacer fuera del dispositivo a través de MDM o cerca del dispositivo después de exportar los registros de diagnóstico de MDM recopilados a través de Configuración Accounts Access work or school (Acceso a cuentas de Configuración trabajo o escuela), y seleccione Export your management logs and viewed on **a** nearby PC (Exportar los registros de administración y verlos en un equipo  ->    >  cercano). 

Ahora los diagnósticos de MDM se pueden ver en el dispositivo mediante el explorador Edge. Para ver más fácilmente el informe de diagnóstico de MDM, vaya a la página Acceso profesional o educativo y seleccione **Ver informe de diagnóstico avanzado**. Esto generará y abrirá el informe en una nueva ventana de Edge.

![Vea el informe de diagnóstico avanzado en Configuración aplicación.](./images/view-advanced-diagnostic-report.jpg)

### <a name="offline-diagnostics-notifications"></a>Notificaciones de diagnóstico sin conexión

Se trata de una actualización de una característica existente denominada [Diagnósticos sin conexión.](hololens-diagnostic-logs.md#offline-diagnostics) Anteriormente, no había ningún indicador claro para los usuarios de que habían desencadenado la recopilación de diagnóstico o que se había completado.
Ahora agregados en Windows compilaciones de Insider, hay dos formas de comentarios sobre el diagnóstico sin conexión. El primero es notificaciones del sistema que se muestran para cuando se inicia y se completa la recopilación. Se mostrarán cuando el usuario haya iniciado sesión y tenga objetos visuales.

![Notificación del sistema para recopilar registros.](./images/logcollection1.jpg)

![Notificación del sistema cuando se completa la recopilación de registros.](./images/logcollection2.jpg)
 
Dado que los usuarios a menudo usan diagnósticos sin conexión como mecanismo de recopilación de registros de reserva para cuando no tienen acceso a una pantalla, no pueden iniciar sesión o todavía están en la OOBE, también habrá una indicación de audio que se reproducirá cuando se recopilibrán los registros. Este sonido se reproducirá además de la notificación del sistema.

Esta nueva característica se habilitará cuando el dispositivo se actualice y no es necesario habilitarla ni administrarla. En cualquier caso de que no se puedan mostrar ni escuchar estos nuevos comentarios, se seguirá generando diagnóstico sin conexión.

Esperamos que con esta adición más reciente de comentarios sobre el lenguaje sea más fácil recopilar datos de diagnóstico y poder solucionar los problemas más rápidamente.

### <a name="use-only-private-store-apps-for-microsoft-store"></a>Usar solo aplicaciones de la tienda privada para Microsoft Store

La directiva RequirePrivateStoreOnly se ha habilitado para HoloLens. Esta directiva permite configurar Microsoft Store aplicación para mostrar solo el almacén privado configurado para su organización. Limitar el acceso solo a las aplicaciones que ha puesto a disposición.

Más información sobre [ApplicationManagement/RequirePrivateStoreOnly](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

### <a name="low-storage-log-collection-improvements"></a>Mejoras en la recopilación de registros de almacenamiento bajo

En escenarios en los que un dispositivo parece tener poco espacio en disco cuando se recopilan los registros de diagnóstico, se creará un informe adicional denominado **StorageDiagnostics.zip.** El umbral de almacenamiento bajo se determina automáticamente Windows [de almacenamiento.](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48)

### <a name="fixes-and-improvements"></a>Correcciones y mejoras

- Se ha [corregido un problema conocido Portal de dispositivos en el que no había ningún mensaje que descargara archivos bloqueados.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- Se ha corregido un problema conocido para Portal de dispositivos con los tiempos de espera de [carga y descarga de archivos.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)
- Soluciona problemas relacionados con la información de las propiedades de cumplimiento de HoloLens dispositivos; puede ser necesario reiniciar para que se desencadene la generación de informes correcta en las compilaciones de Insider.  
- Se ha actualizado la versión de Remote Assist que se instala en flashes nuevos.

## <a name="start-receiving-insider-builds"></a>Empezar a recibir compilaciones de Insider

> [!NOTE]
> Si no se ha actualizado recientemente, reinicie el dispositivo para actualizar el estado y obtener la compilación más reciente.
> - El comando de voz "Reiniciar dispositivo" funciona bien. 
> - También puede elegir el botón reiniciar en Configuración/Windows Programa Insider.
>
> Hemos tenido un error en el back-end que es posible que haya encontrado y esto le permitirá volver a realizar el seguimiento.

En un HoloLens 2, vaya **a Configuración** Update & Security Windows Programa Insider y  >    >   seleccione **Introducción.** Vincule la cuenta que usó para registrarse como Windows Insider.

Windows insider se está moviendo a Canales. El **anillo** rápido se convertirá en  el canal **de desarrollo,** el  anillo lento se convertirá en el **Canal beta** y el anillo versión preliminar se convertirá en el canal de versión preliminar de la **versión .** Este es el aspecto de esa asignación:

![Windows Explicación de los canales de Insider](images/WindowsInsiderChannels.png)

Para obtener más información, vea Introducing Windows Insider Channels (Introducción [a los canales de Insider)](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) Windows Blogs.
A continuación, seleccione Desarrollo **activo de Windows**, elija si desea recibir canal **de** desarrollo o Canal beta **compilaciones** y revise los términos del programa.
Seleccione **Confirmar > Reiniciar ahora** para finalizar. Una vez reiniciado el dispositivo, vaya a Configuración > **Update & Security > Check for updates** to get the latest build (Buscar actualizaciones para obtener la compilación más reciente).

### <a name="update-error-0x80070490-work-around"></a>Actualización de la 0x80070490 de errores

Si se produce un error de actualización 0x80070490 al actualizar en el canal Dev o Beta, pruebe el siguiente trabajo a corto plazo. Implica mover el canal insider, seleccionar la actualización y, a continuación, volver a mover el canal insider.

#### <a name="stage-one---release-preview"></a>Fase uno: versión preliminar

1.  Configuración, Update & Security, Windows Programa Insider, seleccione Release **Preview Channel (Canal de versión preliminar de versión preliminar).**

2.  Configuración, Update & Security, Windows Update, **Check for updates**. Después de la actualización, continúe con la fase dos.

#### <a name="stage-two---dev-channel"></a>Fase dos: Canal de desarrollo

1. Configuración, Actualizar & Seguridad, Windows Programa Insider, seleccione Canal **de desarrollo.**

2. Configuración, Update & Security, Windows Update, **Check for updates**.

## <a name="ffu-download-and-flash-directions"></a>Instrucciones de descarga y flash de FFU

Para probar con un vuelo firmado con ffu, primero debe desbloquear el dispositivo antes de parpadear el vuelo firmado ffu.

1. En pc:
    1. Descargue ffu en el equipo desde [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .
    
    1. Instale ARC (Advanced Recovery Companion) desde la Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .
    
1. En HoloLens: desbloqueo de vuelo: abra **Configuración** Update & Security Windows Programa Insider y, a continuación, regístrese  >    >   y reinicie el dispositivo.

1. Flash FFU: ahora puede flashear el vuelo firmado con FFU mediante ARC.

### <a name="provide-feedback-and-report-issues"></a>Proporcionar comentarios e informar de problemas

Use la [aplicación Centro de opiniones en](hololens-feedback.md) su HoloLens para proporcionar comentarios e informar de problemas. El Centro de opiniones garantiza que se incluye toda la información de diagnóstico necesaria para ayudar a nuestros ingenieros a depurar y resolver rápidamente el problema.  Los problemas con la versión en chino y japonés HoloLens deben informarse de la misma manera.

> [!NOTE]
> Asegúrese de aceptar el mensaje que le pregunta si desea Centro de opiniones acceso a la carpeta Documentos **(seleccione Sí cuando** se le solicite).

## <a name="note-for-developers"></a>Nota para desarrolladores

Le recomendamos que pruebe a desarrollar sus aplicaciones mediante las compilaciones de Insider de HoloLens.  Consulte la documentación [HoloLens developer para](https://developer.microsoft.com/windows/mixed-reality/development) empezar. Esas mismas instrucciones funcionan con las compilaciones de Insider de HoloLens.  Puede usar las mismas compilaciones de Unity y Visual Studio que ya usa para el HoloLens desarrollo.

## <a name="stop-receiving-insider-builds"></a>Dejar de recibir compilaciones de Insider

Si ya no quiere recibir compilaciones de Insider de Windows Holographic, puede optar por no recibir cuando [](hololens-recovery.md) HoloLens ejecuta una compilación de producción o puede recuperar el dispositivo mediante advanced recovery Companion para recuperar el dispositivo en una versión que no sea Insider de Windows Holographic.

> [!CAUTION]
> Hay un problema conocido en el que los usuarios que no se inscriban en las compilaciones de Insider Preview después de volver a instalar manualmente una nueva compilación de versión preliminar experimentarían una pantalla azul. Después, deben recuperar manualmente su dispositivo. Para obtener información completa sobre si se vería afectado o no, consulte más información sobre [este problema conocido.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)

Para comprobar que el HoloLens está ejecutando una compilación de producción:

1. Vaya a **Configuración > System > Acerca de** y busque el número de compilación.

1. [Consulte las notas de la versión de los números de compilación de producción.](hololens-release-notes.md)

Para no participar en las compilaciones de Insider:

1. En un HoloLens una compilación de producción, vaya a Configuración > **Update & Security > Windows Programa Insider** y seleccione Stop Insider builds (Detener compilaciones de **Insider).**

1. Siga las instrucciones para no participar en el dispositivo.
