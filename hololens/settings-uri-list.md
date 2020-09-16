---
title: URI de configuración
description: Lista de URI compatibles con HoloLens para PageVisibilityList
author: evmill
ms.author: v-evmill
ms.date: 8/1/2020
ms.topic: article
keywords: hololens, hololens 2, acceso asignado, quiosco, página de configuración
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: widuff
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 6b506b36915c8f34b90c455410db67e55a2cca09
ms.sourcegitcommit: 7f48e7103f869a22a0d20a54dc8f9b708b22484c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2020
ms.locfileid: "10963724"
---
# URI de configuración

Una de las características que se puede administrar para los dispositivos HoloLens usa la Directiva [Settings/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) para restringir las páginas que se muestran en la aplicación Configuración. Los dispositivos HoloLens y Windows 10 tienen una selección de páginas diferente en la aplicación Configuración. En esta página, solo encontrará la configuración que existe en HoloLens. 

## Cuentas
| Página de configuración           | URI                                            |
|-------------------------|------------------------------------------------|
| Opciones de inicio de sesión         | ms-settings:signinoptions                      |
| Inscripción de Iris       | ms-settings:signinoptions-launchirisenrollment |
| Acceder a la red del trabajo o colegio | ms-settings:workplace                          |

## Dispositivos
| Página de configuración | URI                          |
|---------------|------------------------------|
| Bluetooth     | ms-settings:bluetooth <br> ms-settings:connecteddevices |

## Privacidad
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

## Redes e Internet
| Página de configuración | URI                              |
|---------------|----------------------------------|
| Wi-Fi  | ms-settings:network-wifi<br>ms-settings:network-wifisettings<br>ms-settings:network-status<br>ms-settings:wifi-provisioning    |
| VPN   | ms-settings:network-vpn          |
| Proxy | ms-settings:network-proxy        |

## Sistema
| Página de configuración      | URI                                |
|--------------------|------------------------------------|
| Experiencias compartidas | ms-settings:crossdevice            |
| Colores             | ms-settings:colors<br>ms-settings:personalization-colors |
| Notificaciones y acciones  | ms-settings:notifications          |
| Almacenamiento            | ms-settings:storagesense           |

## Hora e idioma
| Página de configuración | URI                                           |
|---------------|-----------------------------------------------|
| Region        | ms-settings:regionformatting                  |
| Idioma      | ms-settings:regionlanguage<br>ms-settings:regionlanguage-adddisplaylanguage<br>ms-settings:regionlanguage-setdisplaylanguage |

## Actualización y seguridad
| Página de configuración                         | URI                                       |
|---------------------------------------|-------------------------------------------|
| Programa Windows Insider               | ms-settings:windowsinsider <br>ms-settings:windowsinsider-optin          |
| Windows Update                        | ms-settings:windowsupdate<br> ms-settings:windowsupdate-activehours  <br> ms-settings:windowsupdate-history <br> ms-settings:windowsupdate-optionalupdates <br><sup>1</sup>ms-settings:windowsupdate-options<br><sup>1</sup>ms-settings:windowsupdate-restartoptions |
| Windows Update: comprueba si hay actualizaciones. | ms-settings:windowsupdate-action          |
| Opciones avanzadas                    | ms-settings:windowsupdate-options         |

> [!NOTE]
>  1 Los dos URI siguientes no le llevan a la página de Opciones u Opciones avanzadas, solo bloquearán / mostrarán la página principal de Windows Update. 
> - ms-settings:windowsupdate-options
> - ms-settings:windowsupdate-restartoptions 

Para obtener una lista completa de los URI de configuración de Windows 10, visite [aquí](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference). 
