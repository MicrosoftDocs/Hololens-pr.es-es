---
title: Visibilidad de la configuración de página
description: Manténgase al día con nuestra lista de URI compatibles para PageVisibilityList y guía en dispositivos Microsoft HoloLens de realidad mixta.
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
ms.openlocfilehash: f004f39f4b69748e8c36ad93111f4423d14c40f3
ms.sourcegitcommit: 23ee06b659d7a51f3000d386c8f67cbf212d5aa4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2021
ms.locfileid: "11327394"
---
# Visibilidad de la configuración de página

Una de las características que se puede administrar para los dispositivos HoloLens usa la Directiva [Settings/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) para restringir las páginas que se muestran en la aplicación Configuración. PageVisibilityList es una directiva mediante la cual los administradores de TI pueden evitar que páginas específicas de la aplicación Configuración del sistema sean visibles o accesibles, o bien pueden hacer lo sean en todas las páginas excepto en aquellas especificadas.

> [!NOTE]
> Esta característica está disponible solo en [Windows Holographic, versión 20H2](hololens-release-notes.md#windows-holographic-version-20h2) para dispositivos HoloLens 2. Asegúrese de que los dispositivos para los que deseas usar esta versión estén actualizados.

> [!NOTE]
> Pronto serán agregadas más de 20 SettingsURIs nuevas, Consulte[ la página de Windows Insider: nuevas SettingsURIs para la visibilidad de la configuración de la página ](hololens-insider.md#new-settingsuris-for-page-settings-visibility) si está interesado en previsualizar esta configuración en una compilación de [ HoloLens Insider](hololens-insider.md).

En el ejemplo siguiente, se muestra una directiva que permitiría el acceso solo a las páginas Acerca de y de Bluetooth, que tienen el URI "ms-settings:network-wifi" y "ms-settings:bluetooth", respectivamente:
- `showonly:network-wifi;network-proxy;bluetooth`

Para establecer esto a través de un paquete de aprovisionamiento:

1. Al crear su paquete en el diseñador de configuración de Windows, desplácese hasta **Directivas > Configuración > PageVisibilityList**
1. Escriba la cadena: **`showonly:network-wifi;network-proxy;bluetooth`**
1. Exportar el paquete de aprovisionamiento.
1. Aplicar el paquete a su dispositivo.
Para obtener detalles completos sobre cómo crear y aplicar un paquete de aprovisionamiento, e [esta página.](hololens-provisioning.md)

Esto se puede hacer a través de Intune mediante OMA-URI:

1. Crear una **Directiva personalizada**.
1. Al establecer el OMA-URI, use la cadena: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**
1. Al seleccionar los datos, elija: **Cadena**
1. Al escribir el valor, use: **`showonly:network-wifi;network-proxy;bluetooth`**
1. Asegúrese de asignar la configuración del dispositivo personalizado a un grupo en el que el dispositivo esté previsto.

Consulte [la configuración de MDM de HoloLens](hololens-mdm-configure.md) para obtener más información sobre las configuraciones de dispositivos y grupos de Intune.

Independientemente del método elegido, su dispositivo debería recibir ahora los cambios y los usuarios se encontrarán con la siguiente aplicación de Configuración.

![Captura de pantalla de la modificación de las horas activas en la aplicación de Configuración](images/hololens-page-visibility-list.jpg)

Para configurar las páginas de la aplicación Configuración para mostrar u ocultar su propia selección de páginas, eche un vistazo a las URI de configuración disponibles en HoloLens.

## URI de configuración

Los dispositivos HoloLens y Windows 10 tienen una selección de páginas diferente en la aplicación de Configuración. En esta página, solo encontrarás la configuración que existe en HoloLens.

### Cuentas
| Página de configuración           | URI                                            |
|-------------------------|------------------------------------------------|
| Opciones de inicio de sesión         | ` ms-settings:signinoptions `                   |
| Inscripción de Iris       | `ms-settings:signinoptions-launchirisenrollment` |
| Obtener acceso a trabajo o escuela | `ms-settings:workplace`                         |

### Dispositivos
| Página de configuración | URI                          |
|---------------|------------------------------|
| Bluetooth     | `ms-settings:bluetooth` <br> `ms-settings:connecteddevices` |

### Privacidad
| Página de configuración            | URI                                             |
|--------------------------|-------------------------------------------------|
| Información de cuenta             | `ms-settings:privacy-accountinfo`              |
| Diagnóstico de la aplicación        | `ms-settings:privacy-appdiagnostics`              |
| Aplicaciones en segundo plano        | `ms-settings:privacy-backgroundapps`              |
| Movimientos de usuario           | `ms-settings:privacy-backgroundspatialperception` |
| Sistema de archivos              | `ms-settings:privacy-broadfilesystemaccess`       |
| Calendario                 | `ms-settings:privacy-calendar`                    |
| Historial de llamadas             | `ms-settings:privacy-callhistory`                 |
| Contactos                 | `ms-settings:privacy-contacts`                    |
| Otros dispositivos            | `ms-settings:privacy-customdevices`               |
| Documentos                | `ms-settings:privacy-documents`                   |
| Correo electrónico                    | `ms-settings:privacy-email`                       |
| Diagnósticos y comentarios | `ms-settings:privacy-feedback`                    |
| Ubicación                 | `ms-settings:privacy-location`                    |
| Mensajes                | `ms-settings:privacy-messaging`                   |
| Micrófono               | `ms-settings:privacy-microphone`                  |
| Notificaciones            | `ms-settings:privacy-notifications`               |
| Imágenes                 | `ms-settings:privacy-pictures`                    |
| Señales de radio                   | `ms-settings:privacy-radios`                      |
| Voz                   | `ms-settings:privacy-speech`                      |
| Tareas                    | `ms-settings:privacy-tasks`                       |
| Vídeos                   | `ms-settings:privacy-videos`                      |
| Activación por voz       | `ms-settings:privacy-voiceactivation`             |
| Cámara                   | `ms-settings:privacy-webcam`                      |

### Redes e Internet
| Página de configuración | URI                              |
|---------------|----------------------------------|
| Wi-Fi  | `ms-settings:network-wifi`<br>`ms-settings:network-wifisettings`<br>`ms-settings:network-status`<br>`ms-settings:wifi-provisioning`    |
| VPN   | `ms-settings:network-vpn`          |
| Proxy | `ms-settings:network-proxy`        |

### Sistema
| Página de configuración      | URI                                |
|--------------------|------------------------------------|
| Experiencias compartidas | `ms-settings:crossdevice`            |
| Colores             | `ms-settings:colors`<br>`ms-settings:personalization-colors` |
| Notificaciones y acciones  | `ms-settings:notifications`          |
| Almacenamiento            | `ms-settings:storagesense`           |

### Hora e idioma
| Página de configuración | URI                                           |
|---------------|-----------------------------------------------|
| Region        | `ms-settings:regionformatting`                  |
| Idioma      | `ms-settings:regionlanguage`<br>`ms-settings:regionlanguage-adddisplaylanguage`<br>`ms-settings:regionlanguage-setdisplaylanguage` |

### Actualización y seguridad
| Página de configuración                         | URI                                       |
|---------------------------------------|-------------------------------------------|
| Programa Windows Insider               | `ms-settings:windowsinsider` <br>`ms-settings:windowsinsider-optin`          |
| Windows Update                        | `ms-settings:windowsupdate`<br> `ms-settings:windowsupdate-activehours`  <br> `ms-settings:windowsupdate-history` <br> `ms-settings:windowsupdate-optionalupdates` <br><sup>1</sup>`ms-settings:windowsupdate-options`<br><sup>1</sup>`ms-settings:windowsupdate-restartoptions` |
| Windows Update: comprueba si hay actualizaciones. | `ms-settings:windowsupdate-action`          |
| Opciones avanzadas                    | `ms-settings:windowsupdate-options`         |

>  <sup>1</sup> Los dos URI siguientes no le llevan a las páginas de **Opciones avanzadas** u **Opciones**. Solo bloquearán o mostrarán la página principal de Windows Update.
> - ms-settings:windowsupdate-options
> - ms-settings:windowsupdate-restartoptions 

Para obtener una lista completa de uri de configuración de Windows 10, visita la documentación de [configuración de inicio](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference).
