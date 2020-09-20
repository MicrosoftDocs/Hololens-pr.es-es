---
title: Visibilidad de la configuración de página
description: Lista de URI compatibles con HoloLens para PageVisibilityList y Guía
author: evmill
ms.author: v-evmill
ms.date: 09/16/2020
ms.topic: article
keywords: hololens, hololens 2, acceso asignado, quiosco, página de configuración
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: widuff
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 7a24d64b0b60be9f922260b7145d04c2c13951ed
ms.sourcegitcommit: 8b5e349990ba5566bcc6a2a72ff83d1a21b099b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2020
ms.locfileid: "11026943"
---
# Visibilidad de la configuración de página

Una de las características que se puede administrar para los dispositivos HoloLens usa la Directiva [Settings/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) para restringir las páginas que se muestran en la aplicación Configuración. PageVisibilityList es una directiva mediante la cual los administradores de TI pueden evitar que páginas específicas de la aplicación Configuración del sistema sean visibles o accesibles, o bien pueden hacer lo sean en todas las páginas excepto en aquellas especificadas. 

> [!IMPORTANT]
> Actualmente, esta característica solo está disponible en las [compilaciones de Windows Insider](hololens-insider.md). Asegúrese de que los dispositivos con los que vaya a usar esta directiva estén en la compilación 19041.1349+.

En el ejemplo siguiente, se muestra una directiva que permitiría el acceso solo a las páginas Acerca de y de Bluetooth, que tienen el URI "ms-settings:network-wifi" y "ms-settings:bluetooth", respectivamente:
- showonly:network-wifi;network-proxy;bluetooth

Para establecer esto mediante un paquete de aprovisionamiento: 
1. Durante la creación de un paquete en el Diseñador de configuraciones de Windows, desplácese hasta **Directivas > Configuración > PageVisibilityList**
1. Escriba la cadena: **showonly:network-wifi;network-proxy;bluetooth**
1. Exporte el paquete de aprovisionamiento.
1. Aplicar el paquete de aprovisionamiento a su dispositivo. Para todos los detalles sobre cómo crear y aplicar un paquete de aprovisionamiento, visite [esta página](hololens-provisioning.md). 

Se puede realizar mediante Intune con OMA-URI.
1. Crear una **Directiva personalizada**.
1. Al establecer OMA-URI, utilice la cadena: **./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList**
1. Al seleccionar los datos, elija: **Cadena**
1. Al escribir el valor, utilice: **showonly:network-wifi;network-proxy;bluetooth**
1. Asegúrese de asignar la configuración personalizada del dispositivo a un grupo al que se va a destinar el dispositivo.
Encontrará más información sobre los grupos de Intune y las configuraciones de dispositivo [aquí](hololens-mdm-configure.md).

Independientemente del método elegido, el dispositivo debería recibir los cambios ahora y se mostrará a los usuarios la siguiente aplicación Configuración. 

![Captura de pantalla de la modificación de las horas activas en la aplicación Configuración](images/hololens-page-visibility-list.jpg)

Para configurar las páginas de la aplicación Configuración para mostrar u ocultar su propia selección de páginas, eche un vistazo a los URI de configuración disponibles en HoloLens. 

## URI de configuración

Los dispositivos HoloLens y Windows 10 tienen una selección de páginas diferente en la aplicación Configuración. En esta página, solo encontrará la configuración que existe en HoloLens. 

### Cuentas
| Página de configuración           | URI                                            |
|-------------------------|------------------------------------------------|
| Opciones de inicio de sesión         | ms-settings:signinoptions                      |
| Inscripción de Iris       | ms-settings:signinoptions-launchirisenrollment |
| Acceder a la red del trabajo o colegio | ms-settings:workplace                          |

### Dispositivos
| Página de configuración | URI                          |
|---------------|------------------------------|
| Bluetooth     | ms-settings:bluetooth <br> ms-settings:connecteddevices |

### Privacidad
| Página de configuración            | URI                                             |
|--------------------------|-------------------------------------------------|
| Información de cuenta             | ms-settings:privacy-accountinfo                 |
| Diagnóstico de la aplicación        | ms-settings:privacy-appdiagnostics              |
| Aplicaciones en segundo plano        | ms-settings:privacy-backgroundapps              |
| Movimientos de usuario           | ms-settings:privacy-backgroundspatialperception |
| Sistema de archivos              | ms-settings:privacy-broadfilesystemaccess       |
| Calendario                 | ms-settings:privacy-calendar                    |
| Historial de llamadas             | ms-settings:privacy-callhistory                 |
| Contactos                 | ms-settings:privacy-contacts                    |
| Otros dispositivos            | ms-settings:privacy-customdevices               |
| Documentos                | ms-settings:privacy-documents                   |
| Correo electrónico                    | ms-settings:privacy-email                       |
| Diagnósticos y comentarios | ms-settings:privacy-feedback                    |
| Ubicación                 | ms-settings:privacy-location                    |
| Mensajes                | ms-settings:privacy-messaging                   |
| Micrófono               | ms-settings:privacy-microphone                  |
| Notificaciones            | ms-settings:privacy-notifications               |
| Imágenes                 | ms-settings:privacy-pictures                    |
| Señales de radio                   | ms-settings:privacy-radios                      |
| Voz                   | ms-settings:privacy-speech                      |
| Tareas                    | ms-settings:privacy-tasks                       |
| Vídeos                   | ms-settings:privacy-videos                      |
| Activación por voz       | ms-settings:privacy-voiceactivation             |
| Cámara                   | ms-settings:privacy-webcam                      |

### Redes e Internet
| Página de configuración | URI                              |
|---------------|----------------------------------|
| Wi-Fi  | ms-settings:network-wifi<br>ms-settings:network-wifisettings<br>ms-settings:network-status<br>ms-settings:wifi-provisioning    |
| VPN   | ms-settings:network-vpn          |
| Proxy | ms-settings:network-proxy        |

### Sistema
| Página de configuración      | URI                                |
|--------------------|------------------------------------|
| Experiencias compartidas | ms-settings:crossdevice            |
| Colores             | ms-settings:colors<br>ms-settings:personalization-colors |
| Notificaciones y acciones  | ms-settings:notifications          |
| Almacenamiento            | ms-settings:storagesense           |

### Hora e idioma
| Página de configuración | URI                                           |
|---------------|-----------------------------------------------|
| Region        | ms-settings:regionformatting                  |
| Idioma      | ms-settings:regionlanguage<br>ms-settings:regionlanguage-adddisplaylanguage<br>ms-settings:regionlanguage-setdisplaylanguage |

### Actualización y seguridad
| Página de configuración                         | URI                                       |
|---------------------------------------|-------------------------------------------|
| Programa Windows Insider               | ms-settings:windowsinsider <br>ms-settings:windowsinsider-optin          |
| Windows Update                        | ms-settings:windowsupdate<br> ms-settings:windowsupdate-activehours  <br> ms-settings:windowsupdate-history <br> ms-settings:windowsupdate-optionalupdates <br><sup>1</sup>ms-settings:windowsupdate-options<br><sup>1</sup>ms-settings:windowsupdate-restartoptions |
| Windows Update: comprueba si hay actualizaciones. | ms-settings:windowsupdate-action          |
| Opciones avanzadas                    | ms-settings:windowsupdate-options         |

>  <sup>1</sup> Los dos URI siguientes no le llevan a las páginas de **Opciones avanzadas** u **Opciones**. Solo bloquearán o mostrarán la página principal de Windows Update. 
> - ms-settings:windowsupdate-options
> - ms-settings:windowsupdate-restartoptions 

Para obtener una lista completa de los URI de configuración de Windows 10, visite [aquí](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference). 
