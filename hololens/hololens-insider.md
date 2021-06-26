---
title: Insider Preview para Microsoft HoloLens
description: Obtenga información sobre cómo empezar a trabajar con compilaciones de Insider y proporcionar comentarios valiosos para nuestra próxima actualización principal del sistema operativo para HoloLens.
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
ms.openlocfilehash: a4949ab68121cb772fdb8a62411ed70868a6ccb6
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924373"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Insider Preview para Microsoft HoloLens

Le damos la bienvenida a las últimas compilaciones de Insider Preview para HoloLens. Es fácil empezar a trabajar [y proporcionar](hololens-insider.md#start-receiving-insider-builds) comentarios valiosos para nuestra próxima actualización importante del sistema operativo para HoloLens.

## <a name="windows-insider-release-notes"></a>Windows Insider notas de la versión

Nos complace empezar a pasar nuevas características a Windows Insiders de nuevo. Las nuevas compilaciones pasarán a los canales de desarrollo y beta para las actualizaciones más recientes. Seguiremos actualizando esta página a medida que agreguemos más características y actualizaciones a nuestras Windows Insider compilaciones. Prepárese para mezclar estas actualizaciones en su realidad. 

### <a name="csp-changes-on-hololens"></a>Cambios de CSP en HoloLens
 
- Introducido en Windows Insider compilación, 20348.1403

#### <a name="devdetail-csp"></a>DevDetail CSP

Csp de DevDetail ahora también notifica espacio de almacenamiento libre en el dispositivo HoloLens. Debe coincidir aproximadamente con el valor que se muestra en la página Almacenamiento de la aplicación de configuración. A continuación se muestra el nodo específico que contiene esta información.

- ./DevDetail/Ext/Microsoft/FreeStorage (solo operación GET)

#### <a name="devicestatus-csp"></a>DeviceStatus CSP

Csp de DeviceStatus ahora también notifica SSID y BSSID de la red Wifi con la que HoloLens está conectado activamente. A continuación se incluyen los nodos específicos que contienen esta información.

- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*dirección mac de Wi-Fi adaptador*/SSID
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

### <a name="fixes-and-improvements"></a>Correcciones y mejoras:

- Se ha [corregido un problema conocido Portal de dispositivos donde no había ningún mensaje que descargara archivos bloqueados.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- Se ha corregido un problema conocido para Portal de dispositivos con tiempos de espera de [carga y descarga de archivos.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)

## <a name="start-receiving-insider-builds"></a>Empezar a recibir compilaciones de Insider
> [!NOTE]
> Si no ha actualizado recientemente, reinicie el dispositivo para actualizar el estado y obtener la compilación más reciente.
> - El comando de voz "Reiniciar dispositivo" funciona bien. 
> - También puede elegir el botón reiniciar en Configuración/Programa Windows Insider.
>
> Hemos tenido un error en el back-end que puede haber encontrado y esto le permitirá volver a realizar el seguimiento.

En un dispositivo HoloLens 2, vaya a **Configuración**  >  **Update & Security**  >  **Programa Windows Insider** y seleccione **Introducción.** Vincule la cuenta que usó para registrarse como Windows Insider.
Windows Insider ahora se mueve a Canales. El **anillo** rápido se convertirá en  el canal  **de** desarrollo, el  anillo lento se convertirá en el Canal beta y el anillo versión preliminar se convertirá en el canal de versión preliminar **de versión preliminar.** Este es el aspecto de esa asignación: Windows Insider Channels explanation (Explicación de canales de Windows Insider) Para obtener más información, consulte ![ ](images/WindowsInsiderChannels.png) [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs (Introducción a los canales de Windows Insider en blogs de Windows).
A continuación, seleccione Desarrollo activo de **Windows,** elija si desea recibir canal **de** desarrollo o Canal beta **compilaciones** y revise los términos del programa.
Seleccione **Confirmar > Reiniciar ahora** para finalizar. Una vez reiniciado el dispositivo, vaya a Configuración > actualización & seguridad > **Buscar** actualizaciones para obtener la compilación más reciente.
### <a name="update-error-0x80070490-work-around"></a>Actualización de errores 0x80070490 de trabajo
Si se produce un error de actualización 0x80070490 al actualizar en el canal Dev o Beta, pruebe el siguiente trabajo a corto plazo. Implica mover el canal insider, seleccionar la actualización y, a continuación, volver a mover el canal insider.
#### <a name="stage-one---release-preview"></a>Fase uno: versión preliminar
1.  Configuración, Actualizar & seguridad, Programa Windows Insider, seleccione **Release Preview Channel (Canal de versión preliminar).**
2.  Settings, Update & Security, Windows Update, **Check for updates**. Después de la actualización, continúe con la fase dos.
#### <a name="stage-two---dev-channel"></a>Fase dos: Canal de desarrollo
1. Configuración, Actualizar & seguridad, Programa Windows Insider, seleccione **Canal de desarrollo**.
2. Settings, Update & Security, Windows Update, **Check for updates**.
## <a name="ffu-download-and-flash-directions"></a>Instrucciones de descarga y flash de FFU
Para realizar pruebas con un ffu firmado por un vuelo, primero debe desbloquear el dispositivo en vuelo antes de que se abra el ffu firmado por el vuelo.
1. En pc:
    1. Descargue ffu en el equipo desde [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .
    
    1. Instale ARC (Advanced Recovery Companion) desde la Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .
    
1. En HoloLens - Desbloqueo de vuelos: abra La actualización de & seguridad Programa Windows Insider y, a continuación,  >    >   regístrese y reinicie el dispositivo.
1. Flash FFU: ahora puede flashear el vuelo firmado por FFU mediante ARC.
### <a name="provide-feedback-and-report-issues"></a>Proporcionar comentarios e informar de problemas
Use la [aplicación Centro de opiniones en](hololens-feedback.md) HoloLens para proporcionar comentarios y notificar problemas. El Centro de opiniones garantiza que se incluye toda la información de diagnóstico necesaria para ayudar a nuestros ingenieros a depurar y resolver rápidamente el problema.  Los problemas con la versión en chino y japonés de HoloLens deben informarse de la misma manera.
> [!NOTE]
> Asegúrese de aceptar el mensaje que le pregunta si desea Centro de opiniones acceder a la carpeta Documentos (seleccione **Sí** cuando se le solicite).
## <a name="note-for-developers"></a>Nota para desarrolladores
Le recomendamos que pruebe a desarrollar sus aplicaciones mediante compilaciones insider de HoloLens.  Consulte la documentación [para desarrolladores de HoloLens](https://developer.microsoft.com/windows/mixed-reality/development) para empezar. Esas mismas instrucciones funcionan con compilaciones de Insider de HoloLens.  Puede usar las mismas compilaciones de Unity Visual Studio que ya usa para el desarrollo de HoloLens.
## <a name="stop-receiving-insider-builds"></a>Dejar de recibir compilaciones de Insider
Si ya no quiere recibir compilaciones de Insider de Windows Holographic, puede optar por no [](hololens-recovery.md) recibir cuando HoloLens ejecuta una compilación de producción, o bien puede recuperar el dispositivo mediante Advanced Recovery Companion para recuperar el dispositivo en una versión que no sea Insider de Windows Holographic.
> [!CAUTION]
> Hay un problema conocido en el que los usuarios que desascriban las compilaciones de Insider Preview después de volver a instalar manualmente una nueva compilación de versión preliminar experimentarían una pantalla azul. Después, deben recuperar manualmente su dispositivo. Para obtener información completa sobre si se vería afectado o no, consulte más información sobre [este problema conocido.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
Para comprobar que HoloLens ejecuta una compilación de producción:
1. Vaya a **Configuración > sistema > Acerca de** y busque el número de compilación.
1. [Consulte las notas de la versión de los números de compilación de producción.](hololens-release-notes.md)
Para rechazar las compilaciones de Insider:
1. En un dispositivo HoloLens que ejecuta una compilación de producción, vaya a Configuración **> Update & Security > Programa Windows Insider** y seleccione Stop Insider builds (Detener compilaciones de **Insider).**
1. Siga las instrucciones para rechazar el dispositivo.
