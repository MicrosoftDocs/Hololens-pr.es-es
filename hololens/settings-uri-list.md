---
title: Visibilidad de la configuración de páginas
description: Manténgase al día con nuestra lista de URI compatibles con PageVisibilityList y nuestra guía sobre dispositivos de realidad mixta HoloLens.
author: evmill
ms.author: v-evmill
ms.date: 10/13/2020
ms.topic: article
keywords: hololens, hololens 2, acceso asignado, quiosco, página de configuración
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: widuff
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d28994d911532a940d82756aa45609571ee80ac3
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924339"
---
# <a name="page-settings-visibility"></a>Visibilidad de la configuración de páginas

Una de las características administrables para dispositivos HoloLens es usar la directiva [Configuración/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) para restringir las páginas que se ven en la aplicación Configuración. PageVisibilityList es una directiva mediante la cual los administradores de TI pueden evitar que páginas específicas de la aplicación Configuración del sistema sean visibles o accesibles, o bien aplicar dicha restricción a todas las páginas salvo las especificadas.

> [!NOTE]
> Esta característica solo está disponible en la [versión 20H2 de Windows Holographic](hololens-release-notes.md#windows-holographic-version-20h2) o versiones posteriores para dispositivos HoloLens 2. Asegúrese de que los dispositivos para los que tenga intención de usar la característica estén actualizados.

En el ejemplo siguiente se muestra una directiva que únicamente proporcionaría acceso a las páginas "Acerca de" y "Bluetooth", cuyos URI son "ms-settings:network-wifi" y "ms-settings:bluetooth", respectivamente:
- `showonly:network-wifi;network-proxy;bluetooth`

Para definir esta directiva a través de un paquete de aprovisionamiento:

1. Al crear el paquete en el Diseñador de configuración de Windows, vaya a **Directivas > Configuración > PageVisibilityList**.
1. Escriba la siguiente cadena: **`showonly:network-wifi;network-proxy;bluetooth`** .
1. Exporte el paquete de aprovisionamiento.
1. Aplique el paquete al dispositivo.
Para obtener información completa sobre cómo crear y aplicar un paquete de aprovisionamiento, visite [esta página](hololens-provisioning.md).

Esta operación se puede realizar a través de Intune usando OMA-URI. Para ello, siga estos pasos:

1. Cree una **directiva personalizada**.
1. Al establecer el OMA-URI, use la siguiente cadena: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`** .
1. Al seleccionar los datos, elija **Cadena**.
1. Al escribir el valor, use lo siguiente: **`showonly:network-wifi;network-proxy;bluetooth`** .
1. Asegúrese de asignar la configuración de dispositivos personalizada a un grupo al que esté previsto que pertenezca el dispositivo.

Consulte [Configuración de MDM de HoloLens](hololens-mdm-configure.md) para obtener más información sobre los grupos y las configuraciones de dispositivos de Intune.

Independientemente del método elegido, su dispositivo ya debería recibir los cambios. Por su parte, los usuarios se encontrarán con la siguiente aplicación Configuración.

![Captura de pantalla de la modificación de las horas activas en la aplicación Configuración](images/hololens-page-visibility-list.jpg)

Para configurar las páginas de la aplicación Configuración con el fin de mostrar u ocultar su propia selección de páginas, eche un vistazo a los URI de configuración disponibles en HoloLens.

## <a name="settings-uris"></a>URI de configuración

Los dispositivos HoloLens y Windows 10 tienen una selección de páginas diferente en la aplicación Configuración. En esta página, solo encontrará la configuración de HoloLens.

### <a name="accounts"></a>Cuentas
| Página Configuración           | Identificador URI                                            |
|-------------------------|------------------------------------------------|
| Obtener acceso a trabajo o escuela | `ms-settings:workplace`                         |
| Inscripción de iris       | `ms-settings:signinoptions-launchirisenrollment` |
| Opciones de inicio de sesión         | ` ms-settings:signinoptions `                   |

### <a name="apps"></a>Aplicaciones
| Página Configuración | Identificador URI                          |
|---------------|------------------------------|
| Aplicaciones y características<sup>2</sup>     | `ms-settings:appsfeatures` <br> |
| Aplicaciones y características > Opciones avanzadas <sup>2</sup>     | `ms-settings::appsfeatures-app` <br> |
| Aplicaciones y características > Mapas sin conexión <sup>2</sup>     | `ms-settings:maps-maps` <br> |
| Aplicaciones y características > Mapas sin conexión > Descargar mapas <sup>2</sup>     | `ms-settings:maps-downloadmaps` <br> |

### <a name="devices"></a>Dispositivos
| Página Configuración | Identificador URI                          |
|---------------|------------------------------|
| Bluetooth     | `ms-settings:bluetooth` <br> `ms-settings:connecteddevices` |
| Mouse <sup>2</sup>      | `ms-settings:mouse` <br>  |
| USB <sup>2</sup>      | `ms-settings:usb` <br>  |

### <a name="privacy"></a>Privacidad
| Página Configuración            | Identificador URI                                             |
|--------------------------|-------------------------------------------------|
| Información de cuenta             | `ms-settings:privacy-accountinfo`              |
| Diagnósticos de aplicaciones        | `ms-settings:privacy-appdiagnostics`              |
| Aplicaciones en segundo plano        | `ms-settings:privacy-backgroundapps`              |
| Calendario                 | `ms-settings:privacy-calendar`                    |
| Historial de llamadas             | `ms-settings:privacy-callhistory`                 |
| Cámara                   | `ms-settings:privacy-webcam`                      |
| Contactos                 | `ms-settings:privacy-contacts`                    |
| Comentarios y diagnósticos | `ms-settings:privacy-feedback`                    |
| Documentos                | `ms-settings:privacy-documents`                   |
| Correo electrónico                    | `ms-settings:privacy-email`                       |
| Sistema de archivos              | `ms-settings:privacy-broadfilesystemaccess`       |
| General <sup>2</sup>             | `ms-settings:privacy-general`       |
| Personalización de entrada manuscrita y escritura <sup>2</sup>             | `ms-settings:privacy-speechtyping`       |
| Location                 | `ms-settings:privacy-location`                    |
| Mensajería                | `ms-settings:privacy-messaging`                   |
| Micrófono               | `ms-settings:privacy-microphone`                  |
| Movimiento <sup>2</sup>               | `ms-settings:privacy-motion`                  |
| Notificaciones            | `ms-settings:privacy-notifications`               |
| Otros dispositivos            | `ms-settings:privacy-customdevices`               |
| Imágenes                 | `ms-settings:privacy-pictures`                    |
| Señales de radio                   | `ms-settings:privacy-radios`                      |
| Bordes de capturas de pantalla <sup>2</sup>             | `ms-settings:privacy-graphicsCaptureWithoutBorder`       |
| Capturas de pantalla y aplicaciones <sup>2</sup>             | `ms-settings:privacy-graphicsCaptureProgrammatic`       |
| Voz                   | `ms-settings:privacy-speech`                      |
| Tareas                    | `ms-settings:privacy-tasks`                       |
| Movimientos de usuario           | `ms-settings:privacy-backgroundspatialperception` |
| Vídeos                   | `ms-settings:privacy-videos`                      |
| Activación por voz       | `ms-settings:privacy-voiceactivation`             |

### <a name="network--internet"></a>Red e Internet
| Página Configuración | Identificador URI                              |
|---------------|----------------------------------|
| Modo avión <sup>2</sup> | `ms-settings:network-airplanemode`        |
| Proxy | `ms-settings:network-proxy`        |
| VPN   | `ms-settings:network-vpn`          |
| Wi-Fi  | `ms-settings:network-wifi`<br>`ms-settings:network-wifisettings`<br>`ms-settings:network-status`<br>`ms-settings:wifi-provisioning`    |



### <a name="system"></a>Sistema
| Página Configuración      | Identificador URI                                |
|--------------------|------------------------------------|
| Batería <sup>2</sup>           | `ms-settings:batterysaver`<br>|
| Batería <sup>2</sup>           | `ms-settings:batterysaver-settings`<br>|
| Colores             | `ms-settings:colors`<br>`ms-settings:personalization-colors` |
| Hologramas <sup>2</sup>  |  `ms-settings:holograms`  |
| Calibración <sup>2</sup> |  `ms-settings:calibration` |
| Notificaciones y acciones  | `ms-settings:notifications`          |
| Experiencias compartidas | `ms-settings:crossdevice` 
| Sonido <sup>2</sup>           | `ms-settings:sound`<br>|
| Sonido > Volumen de aplicaciones y preferencia de dispositivos <sup>2</sup>           | `ms-settings:apps-volume`<br>|
| Sonido > Administrar dispositivos de sonido <sup>2</sup>           | `ms-settings:sound-devices`<br>|
| Storage            | `ms-settings:storagesense`           |
| Almacenamiento > Configurar sensor de almacenamiento <sup>2</sup>           | `ms-settings:storagepolicies`<br>|

### <a name="time--language"></a>Hora e idioma
| Página Configuración | Identificador URI                                           |
|---------------|-----------------------------------------------|
| Fecha y hora <sup>2</sup> | `ms-settings:dateandtime`                  |
| Teclado <sup>2</sup> | `ms-settings:keyboard`                  |
| Idioma <sup>2</sup> | `ms-settings:language`                  |
| Idioma <sup>2</sup> | `ms-settings:regionlanguage-languageoptions`                  |
| Idioma      | `ms-settings:regionlanguage`<br>`ms-settings:regionlanguage-adddisplaylanguage`<br>`ms-settings:regionlanguage-setdisplaylanguage` |
| Region        | `ms-settings:regionformatting`                  |

### <a name="update--security"></a>Actualización y seguridad
| Página Configuración                         | Identificador URI                                       |
|---------------------------------------|-------------------------------------------|
| Opciones avanzadas                    | `ms-settings:windowsupdate-options`         |
| Restablecimiento y recuperación <sup>2</sup>      | `ms-settings:reset`         |
| Programa Windows Insider               | `ms-settings:windowsinsider` <br>`ms-settings:windowsinsider-optin`          |
| Windows Update                        | `ms-settings:windowsupdate`<br> `ms-settings:windowsupdate-activehours`  <br> `ms-settings:windowsupdate-history` <br> `ms-settings:windowsupdate-optionalupdates` <br><sup>1</sup>`ms-settings:windowsupdate-options`<br><sup>1</sup>`ms-settings:windowsupdate-restartoptions` |
| Windows Update (búsqueda de actualizaciones) | `ms-settings:windowsupdate-action`          |


- <sup>1</sup> - En el caso de versiones de Windows Holographic anteriores a la 21H1, los dos URI siguientes no llevan realmente a las páginas **Opciones avanzadas** u **Opciones**; solo bloquearán o mostrarán la página principal de Windows Update.
  -  ms-settings:windowsupdate-options
  -  ms-settings:windowsupdate-restartoptions

- <sup>2</sup> - Disponible en Windows Holographic 21H1 o versiones posteriores.


Para obtener una lista completa de los URI de Configuración de Windows 10, consulte la documentación de la [configuración de inicio](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference).
