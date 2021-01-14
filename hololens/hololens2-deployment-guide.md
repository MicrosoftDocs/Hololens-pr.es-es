---
title: Guía de implementación de clientes externos
description: Guía de implementación de HoloLens 2 para clientes externos (con asistencia remota como ejemplo)
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
ms.topic: article
ms.localizationpriority: medium
ms.date: 1/12/2021
ms.custom: ''
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: c0ea468df2188700af408803ae1c55b9d0e4c763
ms.sourcegitcommit: ea5fa6c970756025b77c00b4ea600d60ce033106
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2021
ms.locfileid: "11268006"
---
# Implementar HoloLens 2 en clientes externos con asistencia remota

Este documento ayuda a las profesiones de TI a planear e implementar dispositivos HoloLens 2 centrados en el asistente remoto. [Obtenga más información sobre asistencia remota.](https://docs.microsoft.com/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist)

## Descripción del escenario

Para este documento, Contoso Company desea enviar un dispositivo HoloLens 2 a la planta de un cliente externo para su uso a corto o largo plazo. Cuando el cliente necesita asistencia para el mantenimiento, el cliente inicia sesión en el dispositivo HoloLens 2 con las credenciales proporcionadas por contoso Company y usa asistencia remota para ponerse en contacto con los expertos de Contoso Company.

### Requisitos para este escenario

1. [Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. Administrador de dispositivos móviles, como [Intune](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)
1. Licencia de asistencia remota
    1. [Comprar asistencia remota](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
    1. [Asistente remoto de prueba](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)

## Preocupaciones comunes

- [Cómo garantizar que los clientes externos no puedan comunicarse entre sí](#how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another)
- [Cómo asegurarse de que los clientes no tienen acceso a los recursos de la empresa](#how-to-ensure-that-clients-do-not-have-access-to-company-resources)
- [Cómo restringir aplicaciones](#how-to-restrict-apps)
- [Cómo administrar contraseñas](#how-to-manage-passwords)
- [Cómo asegurarse de que los clientes no tienen acceso al historial de chat](#how-to-ensure-that-clients-do-not-have-access-to-chat-history)

### Cómo garantizar que los clientes externos no puedan comunicarse entre sí

Dado que las llamadas de HoloLens de asistencia remota a HoloLens no son compatibles, los clientes pueden buscar, pero no pueden comunicarse entre sí. Para restringir aún más los clientes que pueden buscar y llamar, las  [barreras](https://docs.microsoft.com/microsoft-365/compliance/information-barriers?view=o365-worldwide) de información pueden restringir con quién se puede comunicar un cliente. Otra opción que se debe tener en cuenta es usar [la búsqueda en directorios con ámbito](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search)

 > [!NOTE]
> Dado que el inicio de sesión único está habilitado, es importante deshabilitar el explorador mediante [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac). Si un cliente externo abre el explorador y usa la versión web de Teams, el cliente tendrá acceso al historial de llamadas y chats.

### Cómo asegurarse de que los clientes no tienen acceso a los recursos de la empresa

Hay dos opciones que se deben tener en cuenta.

La primera opción es un enfoque de varias capas:

1. Asigne solo las licencias que el usuario necesita. Si no asigna OneDrive, Outlook, SharePoint, Yammer, etc., al usuario, no tendrá acceso a esos recursos. Las únicas licencias que necesitarán los usuarios son asistencia remota, Intune y licencias de AAD para comenzar.
1. Bloquear aplicaciones (como el correo electrónico) a las que no desea que los clientes accedan (vea [Cómo restringir aplicaciones).](#how-to-restrict-apps)
1. No comparta nombres de usuario ni contraseñas con los clientes. Para iniciar sesión en HoloLens 2, se requiere un correo electrónico y un PIN numérico.

La segunda opción es crear un inquilino independiente que hospeda clientes (vea la imagen 1.1).

**Imagen 1.1**

![Imagen de inquilino de servicio](./images/hololens-service-tenant-image.png)

### Cómo restringir aplicaciones

[El modo de](https://docs.microsoft.com/hololens/hololens-kiosk) pantalla completa o [WDAC (Windows Defender control](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) de aplicaciones) son opciones para restringir aplicaciones.

### Cómo administrar contraseñas

1. Quitar la expiración de la contraseña. Sin embargo, esto aumenta la posibilidad de que una cuenta se vea comprometida. La recomendación de contraseña de NIST es cambiar las contraseñas cada 30-90 días.
1. Ampliar la expiración de la contraseña para dispositivos HoloLens 2 para que supere los 90 días.
1. Los dispositivos deben devolverse a Contoso para cambiar las contraseñas. Sin embargo, esto puede causar problemas si se espera que los dispositivos estén en la planta del cliente durante más de 90 días.  
1. Para los dispositivos que se envían a varios clientes, restablezca las contraseñas antes de enviar el dispositivo a los clientes.

### Cómo asegurarse de que los clientes no tienen acceso al historial de chat

El asistente remoto borra el historial de chat después de cada sesión. Sin embargo, el historial de chat estará disponible para el usuario de Microsoft Teams.

> [!NOTE]
> Dado que el inicio de sesión único está habilitado, es importante deshabilitar el explorador mediante [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac). Si un cliente externo abre el explorador y usa la versión web de Teams, el cliente tendrá acceso al historial de llamadas y chats.

## Recomendaciones e instrucciones generales de implementación

Te recomendamos lo siguiente para los pasos de implementación de HoloLens 2:

1. Usa la [versión más reciente del sistema operativo HoloLens](https://aka.ms/hololens2download) como compilación de línea base.
1. Asignar licencias basadas en dispositivos o usuarios:
    1. Tanto las licencias basadas en usuarios como las licencias basadas en dispositivos siguen estos pasos:
        1. [Cree un grupo en AAD y agregue miembros para](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) los usuarios de HoloLens/RA.
        1. [Asignar licencias basadas en dispositivos o basadas en](https://docs.microsoft.com/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) usuarios a este grupo.
        1. (Opcional) Puedes seleccionar grupos de destino para las directivas MDM.

1. Los dispositivos deben estar unidos a AAD al espacio empresarial, [inscritos](https://docs.microsoft.com/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)automáticamente y configurados a través del [piloto automático.](https://docs.microsoft.com/hololens/hololens2-autopilot)
    1. Ten en cuenta que el primer usuario del dispositivo será el propietario del dispositivo.
    1. Ten en cuenta que si el dispositivo está unido a AAD, el usuario que realizó la unión se hace propietario del dispositivo.
    1. Para obtener más información, consulta [Propietario del dispositivo.](https://docs.microsoft.com/hololens/security-adminless-os#device-owner)
1. [El inquilino](https://docs.microsoft.com/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) bloquea el dispositivo para que solo pueda unirse a tu espacio empresarial.
    1. **Vínculo adicional: CSP** [de bloqueo de inquilino.](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp)
1. Configurar quiosco con acceso asignado global [aquí.](https://docs.microsoft.com/hololens/hololens-global-assigned-access-kiosk)
1. Se recomienda deshabilitar las siguientes funcionalidades (opcionales):
    1. Capacidad de poner el dispositivo en modo de [desarrollador aquí.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)
    1. Capacidad de conectar HoloLens a un equipo para copiar la fecha [deshabilitar USB.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)
       > [!NOTE]
        > Si no quieres deshabilitar USB, pero quieres poder aplicar un paquete de aprovisionamiento al dispositivo mediante USB, sigue las instrucciones que se indican [**aquí.**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)

1. Usa [WDAC](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) para permitir o aplicaciones en negro en el dispositivo HoloLens 2.
1. Actualice remote Assist a la versión más reciente como parte de la configuración. Hay dos opciones para hacerlo:
    1. Para ello, vaya a Windows **Microsoft Store --> Remote Assist --> y Update App.**
    1. Otro método es dejar HoloLens 2 conectado durante la noche para la actualización automática.
1. [Deshabilite todas las](https://docs.microsoft.com/hololens/settings-uri-list) páginas de configuración excepto la configuración de red para permitir que los usuarios se conecten a redes invitadas en sitios cliente.
1. [Administrar actualizaciones de HoloLens](https://docs.microsoft.com/hololens/hololens-updates)
    1. Opción para [controlar las actualizaciones del sistema operativo](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) o permitir el flujo libremente.
1. [Restricciones comunes de dispositivo.](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)
