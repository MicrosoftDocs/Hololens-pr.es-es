---
title: HoloLens de referencia de quiosco
description: Información y ejemplos de quioscos en HoloLens dispositivos.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 8/24/2021
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 9f8cfd0013ac5b8cf85a334cbb89c458440820d9
ms.sourcegitcommit: 6ce962ede986ebfab21d1665722694eaee13c280
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/25/2021
ms.locfileid: "122863950"
---
# <a name="hololens-kiosk-reference-information"></a>HoloLens Información de referencia de quiosco

Esta página contiene información útil para configurar el modo HoloLens pantalla completa del dispositivo. Estas referencias incluyen AUMIDs para aplicaciones de bandeja de entrada y localización de las de , y varios ejemplos XML para el modo de pantalla completa, que están a solo unas cuantas ediciones de estar listas para usarse en varios escenarios diferentes. Para obtener información sobre cómo configurar un quiosco, lea [la página Configurar un quiosco.](hololens-kiosk.md)

## <a name="hololens-application-user-model-ids-aumids"></a>HoloLens Id. de modelo de usuario de aplicación (AUMID)  

Para obtener información general sobre cómo elegir aplicaciones de quiosco, consulte Directrices para elegir una aplicación para el acceso asignado [(modo de pantalla completa).](/windows/configuration/guidelines-for-assigned-access-app)

Si usa un sistema mobile Administración de dispositivos (MDM) o un paquete de aprovisionamiento para configurar el modo de pantalla completa, use el proveedor de servicios de configuración [(CSP) AssignedAccess](/windows/client-management/mdm/assignedaccess-csp) para especificar aplicaciones. El CSP usa los id. de modelo de usuario [de aplicación (AUMID)](/windows/configuration/find-the-application-user-model-id-of-an-installed-app) para identificar las aplicaciones. En la tabla siguiente se enumeran los AUMID de algunas aplicaciones que se pueden usar en una pantalla completa con varias aplicaciones.

<a id="aumids"></a>

|Nombre de la aplicación |AUMID |
| --- | --- |
|Visor 3D |Microsoft.Microsoft3DViewer \_ 8wekyb3d8bbwe \! Microsoft.Microsoft3DViewer |
|Calendario |microsoft.windowscommunicationsapps \_ 8wekyb3d8bbwe \! microsoft.windowslive.calendar |
|Cámara<sup>1, 2</sup> |HoloCamera \_ cw5n1h2txyewy \! HoloCamera |
|Cortana<sup>3</sup> |Microsoft.549981C3F5F10 \_ 8wekyb3d8bbwe \! App |
|Selector de dispositivos en HoloLens (1.ª generación) |HoloDevicesFlow \_ cw5n1h2txyewy \! HoloDevicesFlow |
|Selector de dispositivos en HoloLens 2 |Microsoft. Windows. DevicesFlowHost \_ cw5n1h2txyewy \! Microsoft.Windows. DevicesFlowHost |
|Dynamics 365 Guides |Microsoft.Dynamics365.Guides \_ 8wekyb3d8bbwe \! MicrosoftGuides |
|Dynamics 365 Remote Assist |Microsoft.MicrosoftRemoteAssist \_ 8wekyb3d8bbwe \! Microsoft.RemoteAssist |
|Centro de &nbsp; comentarios |Microsoft.WindowsFeedbackHub \_ 8wekyb3d8bbwe \! App |
|Explorador de archivos |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App |
|Correo |microsoft.windowscommunicationsapps_8wekyb3d8bbwe!microsoft.windowslive.mail |
|Antiguo Microsoft Edge |Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge |
|Nuevo Microsoft Edge |Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE |
|Microsoft Store |Microsoft.WindowsStore_8wekyb3d8bbwe!App |
|Miracast<sup>4</sup> | &nbsp; |
|Películas y TV |Microsoft.ZuneVideo \_ 8wekyb3d8bbwe \! Microsoft.ZuneVideo |
|OneDrive |microsoft.microsoftskydrive \_ 8wekyb3d8bbwe \! App |
|Fotos |Microsoft. Windows. \_Fotos 8wekyb3d8bbwe \! App |
|Datos Configuración |HolographicSystemSettings_cw5n1h2txyewy! Aplicación |
|Nuevo Configuración |BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! Aplicación |
|Sugerencias |Microsoft.HoloLensTips \_ 8wekyb3d8bbwe \! HoloLensTips |

> <sup>1 Para</sup> habilitar la captura de fotos o vídeos, debe habilitar la aplicación Cámara como una aplicación de quiosco.  
> <sup>2</sup> Al habilitar la aplicación Cámara, tenga en cuenta las condiciones siguientes:
> - El menú Acciones rápidas incluye los botones Foto y Vídeo.
> - También debe habilitar una aplicación (como Fotos, Mail o OneDrive) que pueda interactuar con o recuperar imágenes.  
>  
> <sup>3</sup> Incluso si no habilita la Cortana como una aplicación de pantalla completa, se habilitan los comandos de voz integrados. Sin embargo, los comandos relacionados con las características deshabilitadas no tienen ningún efecto.  
> <sup>4</sup> No se puede habilitar Miracast directamente. Para habilitar Miracast como una aplicación de pantalla completa, habilite la aplicación Cámara y la aplicación Selector de dispositivos.

Además, el Mixed Reality inicio no se puede establecer como una aplicación de quiosco.

Volver a [escenarios admitidos para el modo de pantalla completa en función del tipo de identidad](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

## <a name="kiosk-xml-code-samples"></a>Ejemplos de código XML de quiosco

1. [Perfil de acceso asignado global de varias aplicaciones](#multiple-app-global-assigned-access-profile)
1. [Perfil de acceso asignado global de varias aplicaciones, excepto los propietarios de dispositivos](#multiple-app-global-assigned-access-profile-excluding-device-owners)
1. [Perfil de acceso asignado a varias aplicaciones para una cuenta local o una cuenta de usuario de AAD](#multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account)
1. [Varios perfiles de acceso asignados a la aplicación para dos usuarios de AAD o más](#multiple-app-assigned-access-profiles-for-two-aad-users-or-more)
1. [Perfil de acceso asignado a varias aplicaciones para un grupo de AAD](#multiple-app-assigned-access-profile-for-one-aad-group)
1. [Perfil de acceso asignado a varias aplicaciones para dos grupos de AAD o más](#multiple-app-assigned-access-profile-for-two-aad-groups-or-more)
1. [Perfil de acceso asignado a varias aplicaciones para una cuenta de AAD y un grupo de AAD](#multiple-app-assigned-access-profile-for-one-aad-account-and-one-aad-group)
1. [Perfil de acceso asignado a varias aplicaciones para los visitantes](#multiple-app-assigned-access-profile-for-visitors)

> [!NOTE]
> Reemplace las acciones TODO según sus requisitos.

### <a name="multiple-app-global-assigned-access-profile"></a>Perfil de acceso asignado global de varias aplicaciones

:::code language="xml" source="samples/kiosk-sample-global-multiapp-for-everyone.xml" highlight="18-20":::

[Volver a la lista](#kiosk-xml-code-samples) <br>
Volver a [escenarios admitidos para el modo de pantalla completa en función del tipo de identidad](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-global-assigned-access-profile-excluding-device-owners"></a>Perfil de acceso asignado global de varias aplicaciones, excepto los propietarios de dispositivos

:::code language="xml" source="samples/kiosk-sample-global-multiapp-for-everyone-excluding-device-owners.xml" highlight="18-20":::

[Volver a la lista](#kiosk-xml-code-samples) <br>
Volver a [escenarios admitidos para el modo de pantalla completa en función del tipo de identidad](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account"></a>Perfil de acceso asignado a varias aplicaciones para una cuenta local o una cuenta de usuario de AAD

:::code language="xml" source="samples/kiosk-sample-multi-app-local-or-aad-user.xml" highlight="18-20,51,55":::

[Volver a la lista](#kiosk-xml-code-samples) <br>
Volver a [escenarios admitidos para el modo de pantalla completa en función del tipo de identidad](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profiles-for-two-aad-users-or-more"></a>Varios perfiles de acceso asignados a la aplicación para dos usuarios de AAD o más

:::code language="xml" source="samples/kiosk-sample-multi-app-two-aad-users-or-more.xml" highlight="22-24,52,53,80,88":::

[Volver a la lista](#kiosk-xml-code-samples) <br>
Volver a [escenarios admitidos para el modo de pantalla completa en función del tipo de identidad](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-one-aad-group"></a>Perfil de acceso asignado a varias aplicaciones para un grupo de AAD

:::code language="xml" source="samples/kiosk-sample-multi-app-one-aad-group.xml" highlight="28":::

[Volver a la lista](#kiosk-xml-code-samples) <br>
Volver a [escenarios admitidos para el modo de pantalla completa en función del tipo de identidad](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-two-aad-groups-or-more"></a>Perfil de acceso asignado a varias aplicaciones para dos grupos de AAD o más

:::code language="xml" source="samples/kiosk-sample-multi-app-two-aad-groups-or-more.xml" highlight="22-24,52,53,83,94":::

[Volver a la lista](#kiosk-xml-code-samples) <br>
Volver a [escenarios admitidos para el modo de pantalla completa en función del tipo de identidad](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-one-aad-account-and-one-aad-group"></a>Perfil de acceso asignado a varias aplicaciones para una cuenta de AAD y un grupo de AAD

:::code language="xml" source="samples/kiosk-sample-multi-app-for-aad-user-and-aad-group.xml" highlight="22-24,52,53,80,91":::

[Volver a la lista](#kiosk-xml-code-samples) <br>
Volver a [escenarios admitidos para el modo de pantalla completa en función del tipo de identidad](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-visitors"></a>Perfil de acceso asignado a varias aplicaciones para los visitantes

:::code language="xml" source="samples/kiosk-sample-multi-app-visitor-user.xml" highlight="18-20":::

[Volver a la lista](#kiosk-xml-code-samples) <br>
Volver a [escenarios admitidos para el modo de pantalla completa en función del tipo de identidad](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)
