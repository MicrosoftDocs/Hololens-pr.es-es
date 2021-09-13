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
ms.openlocfilehash: 92040019b093c5ef63d74f095dcb3809112ae7a0
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2021
ms.locfileid: "126034700"
---
# <a name="page-settings-visibility"></a>Visibilidad de la configuración de páginas

Una de las características administrables para dispositivos HoloLens es usar la directiva [Configuración/PageVisibilityList](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) para restringir las páginas que se ven en la aplicación Configuración. PageVisibilityList es una directiva mediante la cual los administradores de TI pueden evitar que páginas específicas de la aplicación Configuración del sistema sean visibles o accesibles, o bien aplicar dicha restricción a todas las páginas salvo las especificadas.

> [!NOTE]
> Esta característica solo está disponible en la [versión 20H2 de Windows Holographic](hololens-release-notes.md#windows-holographic-version-20h2) o versiones posteriores para dispositivos HoloLens 2. Asegúrese de que los dispositivos para los que tenga intención de usar la característica estén actualizados.


## <a name="examples"></a>Ejemplos
Las páginas se identifican mediante una versión abreviada de sus URI publicados, que es el URI menos el prefijo "ms-settings:".

En el ejemplo siguiente se muestra una directiva que únicamente proporcionaría acceso a las páginas "Acerca de" y "Bluetooth", cuyos URI son "network-wifi" y "bluetooth", respectivamente:
- `showonly:network-wifi;network-proxy;bluetooth`

En el ejemplo siguiente se muestra una directiva que ocultaría la página Restablecimiento del sistema operativo:
- `hide:reset`


## <a name="deploying-this-policy-via-intune"></a>Implementación de esta directiva a través de Intune

Estos son los valores de configuración que se suministrarán a Intune:

- **Nombre:** nombre para mostrar preferido del administrador para el perfil.
- **OMA-URI:** URI completo de la página de configuración, incluido su [ámbito](/windows/client-management/mdm/policy-configuration-service-provider). En estos ejemplos de esta página se usa el ámbito `./Device`.
- **Valor:** valor de cadena que indica si se deben ocultar o mostrar *solo* las páginas especificadas. Los valores posibles son `hide:<pagename>` y `showonly:<pagename>`. 
 
Se pueden especificar varias páginas si se separan con un punto y coma. A continuación se puede encontrar una lista de páginas comunes.

1. Cree una **directiva personalizada**.
1. Al establecer el **OMA-URI**, escriba el URI con ámbito completo. Por ejemplo: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**
1. Al seleccionar los datos, elija **Cadena**.
1. Al especificar **Valor**, use las instrucciones anteriores. Por ejemplo, **`showonly:network-wifi;network-proxy;bluetooth`** o **`hide:reset`** . 
> [!IMPORTANT]
> Asegúrese de asignar la configuración de dispositivos personalizada a un grupo al que esté previsto que pertenezca el dispositivo. Si no se realiza este paso, se insertará la directiva, pero no se aplicará.

Consulte [Configuración de MDM de HoloLens](hololens-mdm-configure.md) para obtener más información sobre los grupos y las configuraciones de dispositivos de Intune.


## <a name="deploying-this-policy-via-a-provisioning-package"></a>Implementación de esta directiva a través de un paquete de aprovisionamiento

Estos son los valores de configuración que se especificarán en el Diseñador de configuración de Windows:

**Valor:** valor de cadena que indica si se deben ocultar o mostrar *solo* las páginas especificadas. Los valores posibles son `hide:<pagename>` y `showonly:<pagename>`. Se pueden especificar varias páginas si se separan con un punto y coma. A continuación se puede encontrar una lista de páginas comunes.


1. Al crear el paquete en el Diseñador de configuración de Windows, vaya a **Directivas > Configuración > PageVisibilityList**.
1. Escriba la siguiente cadena: **`showonly:network-wifi;network-proxy;bluetooth`** .
1. Exporte el paquete de aprovisionamiento.
1. Aplique el paquete al dispositivo.
Para obtener información completa sobre cómo crear y aplicar un paquete de aprovisionamiento, visite [la página Aprovisionamiento de HoloLens](hololens-provisioning.md).


Independientemente del método elegido, su dispositivo ya debería recibir los cambios. Por su parte, los usuarios se encontrarán con la siguiente aplicación Configuración.

![Captura de pantalla de la modificación de las horas activas en la aplicación Configuración.](images/hololens-page-visibility-list.jpg)

Para configurar las páginas de la aplicación Configuración con el fin de mostrar u ocultar su propia selección de páginas, eche un vistazo a los URI de configuración disponibles en HoloLens.

## <a name="settings-uris"></a>URI de configuración

Los dispositivos HoloLens y Windows 10 tienen una selección de páginas diferente en la aplicación Configuración. En esta página, solo encontrará la configuración de HoloLens.

### <a name="accounts"></a>Cuentas
| Página Configuración           | Identificador URI                                            |
|-------------------------|------------------------------------------------|
| Obtener acceso a trabajo o escuela | `workplace`                         |
| Inscripción de iris       | `signinoptions-launchirisenrollment` |
| Opciones de inicio de sesión         | ` signinoptions `                   |

### <a name="apps"></a>Aplicaciones
| Página Configuración | Identificador URI                          |
|---------------|------------------------------|
| Aplicaciones y características <sup>2</sup>     | `appsfeatures` <br> |
| Aplicaciones y características > Opciones avanzadas <sup>2</sup>     | `appsfeatures-app` <br> |
| Aplicaciones y características > Mapas sin conexión <sup>2</sup>     | `maps-maps` <br> |
| Aplicaciones y características > Mapas sin conexión > Descargar mapas <sup>2</sup>     | `maps-downloadmaps` <br> |

### <a name="devices"></a>Dispositivos
| Página Configuración | Identificador URI                          |
|---------------|------------------------------|
| Bluetooth     | `bluetooth` <br> `connecteddevices` |
| Mouse <sup>2</sup>      | `mouse` <br>  |
| USB <sup>2</sup>      | `usb` <br>  |

### <a name="privacy"></a>Privacidad
| Página Configuración            | Identificador URI                                             |
|--------------------------|-------------------------------------------------|
| Información de cuenta             | `privacy-accountinfo`              |
| Diagnósticos de aplicaciones        | `privacy-appdiagnostics`              |
| Aplicaciones en segundo plano        | `privacy-backgroundapps`              |
| Calendario                 | `privacy-calendar`                    |
| Historial de llamadas             | `privacy-callhistory`                 |
| Cámara                   | `privacy-webcam`                      |
| Contactos                 | `privacy-contacts`                    |
| Comentarios y diagnósticos | `privacy-feedback`                    |
| Documentos                | `privacy-documents`                   |
| Correo electrónico                    | `privacy-email`                       |
| Sistema de archivos              | `privacy-broadfilesystemaccess`       |
| General <sup>2</sup>             | `privacy-general`       |
| Personalización de entrada manuscrita y escritura <sup>2</sup>             | `privacy-speechtyping`       |
| Location                 | `privacy-location`                    |
| Mensajería                | `privacy-messaging`                   |
| Micrófono               | `privacy-microphone`                  |
| Movimiento <sup>2</sup>               | `privacy-motion`                  |
| Notificaciones            | `privacy-notifications`               |
| Otros dispositivos            | `privacy-customdevices`               |
| Imágenes                 | `privacy-pictures`                    |
| Señales de radio                   | `privacy-radios`                      |
| Bordes de capturas de pantalla <sup>2</sup>             | `privacy-graphicsCaptureWithoutBorder`       |
| Capturas de pantalla y aplicaciones <sup>2</sup>             | `privacy-graphicsCaptureProgrammatic`       |
| Voz                   | `privacy-speech`                      |
| Tareas                    | `privacy-tasks`                       |
| Movimientos de usuario           | `privacy-backgroundspatialperception` |
| Vídeos                   | `privacy-videos`                      |
| Activación por voz       | `privacy-voiceactivation`             |

### <a name="network--internet"></a>Red e Internet
| Página Configuración | Identificador URI                              |
|---------------|----------------------------------|
| Modo avión <sup>2</sup> | `network-airplanemode`        |
| Proxy | `network-proxy`        |
| VPN   | `network-vpn`          |
| Wi-Fi  | `network-wifi`<br>`network-wifisettings`<br>`network-status`<br>`wifi-provisioning`    |



### <a name="system"></a>Sistema
| Página Configuración      | Identificador URI                                |
|--------------------|------------------------------------|
| Batería <sup>2</sup>           | `batterysaver`<br>|
| Batería <sup>2</sup>           | `batterysaver-settings`<br>|
| Colores             | `colors`<br>`personalization-colors` |
| Hologramas <sup>2</sup>  |  `holograms`  |
| Calibración <sup>2</sup> |  `calibration` |
| Notificaciones y acciones  | `notifications`          |
| Experiencias compartidas | `crossdevice` 
| Sonido <sup>2</sup>           | `sound`<br>|
| Sonido > Volumen de aplicaciones y preferencia de dispositivos <sup>2</sup>           | `apps-volume`<br>|
| Sonido > Administrar dispositivos de sonido <sup>2</sup>           | `sound-devices`<br>|
| Storage            | `storagesense`           |
| Almacenamiento > Configurar sensor de almacenamiento <sup>2</sup>           | `storagepolicies`<br>|

### <a name="time--language"></a>Hora e idioma
| Página Configuración | Identificador URI                                           |
|---------------|-----------------------------------------------|
| Fecha y hora <sup>2</sup> | `dateandtime`                  |
| Teclado <sup>2</sup> | `keyboard`                  |
| Idioma <sup>2</sup> | `language`                  |
| Idioma <sup>2</sup> | `regionlanguage-languageoptions`                  |
| Idioma      | `regionlanguage`<br>`regionlanguage-adddisplaylanguage`<br>`regionlanguage-setdisplaylanguage` |
| Region        | `regionformatting`                  |

### <a name="update--security"></a>Actualización y seguridad
| Página Configuración                         | Identificador URI                                       |
|---------------------------------------|-------------------------------------------|
| Opciones avanzadas                    | `windowsupdate-options`         |
| Restablecimiento y recuperación <sup>2</sup>      | `reset`         |
| Programa Windows Insider               | `windowsinsider` <br>`windowsinsider-optin`          |
| Windows Update                        | `windowsupdate`<br> `windowsupdate-activehours`  <br> `windowsupdate-history` <br> `windowsupdate-optionalupdates` <br><sup>1</sup>`windowsupdate-options`<br><sup>1</sup>`windowsupdate-restartoptions` |
| Windows Update (búsqueda de actualizaciones) | `windowsupdate-action`          |


- <sup>1</sup> - En el caso de versiones de Windows Holographic anteriores a la 21H1, los dos URI siguientes no llevan realmente a las páginas **Opciones avanzadas** u **Opciones**; solo bloquearán o mostrarán la página principal de Windows Update.
  -  windowsupdate-options
  -  windowsupdate-restartoptions

- <sup>2</sup> - Disponible en Windows Holographic 21H1 o versiones posteriores.


Para obtener una lista completa de los URI de Configuración de Windows 10, consulte la documentación de la [configuración de inicio](/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference).
