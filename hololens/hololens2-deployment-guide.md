---
title: Implementación de aplicaciones conectadas HoloLens 2 nube en clientes externos
description: Guía de implementación HoloLens 2 para clientes externos (con asistencia remota como ejemplo)
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-qianwen
ms.topic: article
ms.localizationpriority: medium
ms.date: 8/6/2021
ms.custom: ''
ms.reviewer: ''
manager: sekerawa
appliesto:
- HoloLens 2
ms.openlocfilehash: d5cd9c380e0d276f0a8aa9efac14cf44885446e5
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2021
ms.locfileid: "123190334"
---
# <a name="deploy-cloud-connected-hololens-2-to-external-clients"></a>Implementación de aplicaciones conectadas HoloLens 2 nube en clientes externos

Esta guía es un complemento de la [Guía de implementación conectada a la nube](hololens2-cloud-connected-overview.md). Se usa en situaciones en las que su organización quiere enviar HoloLens 2 dispositivos a las instalaciones de un cliente externo para su uso a corto o largo plazo. El cliente externo inicia sesión en el dispositivo HoloLens 2 con las [](/dynamics365/mixed-reality/remote-assist/ra-overview) credenciales proporcionadas por la organización y usa Remote Assist para ponerse en contacto con los expertos. En esta guía se [proporcionan](#general-deployment-recommendations) recomendaciones generales de implementación HoloLens 2 que son [](#common-external-client-deployment-concerns) aplicables a la mayoría de los escenarios de implementación de HoloLens 2 externos y problemas comunes que tienen los clientes al implementar Remote Assist para uso externo. 

## <a name="prerequisites"></a>Prerrequisitos

La siguiente infraestructura debe estar en su lugar según la [Guía de](hololens2-cloud-connected-overview.md) implementación conectada a la nube para implementar el HoloLens 2 externamente.

- Azure AD unirse a la inscripción automática de MDM: administrada por MDM (Intune)
- Los usuarios inician sesión con su propia cuenta corporativa (Azure AD)
    - Se admiten uno o varios usuarios por dispositivo.

### <a name="remote-assist-licensing-and-requirements"></a>Remote Assist licencias y requisitos

- Cuenta de Azure AD (necesaria para comprar la suscripción y asignar licencias)
- [Suscripción a Remote Assist](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (o [prueba de Remote Assist](/dynamics365/mixed-reality/remote-assist/try-remote-assist))

Consulte [Más información sobre Remote Assist](/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist).

### <a name="dynamics-365-remote-assist-user"></a>Usuario de Dynamics 365 Remote Assist

- Licencia de Remote Assist
- Conectividad de red

### <a name="microsoft-teams-user"></a>Usuario de Microsoft Teams

- Microsoft Teams o [Teams Freemium](https://products.office.com/microsoft-teams/free)
- Conectividad de red

## <a name="general-deployment-recommendations"></a>Recomendaciones generales de implementación

Se recomiendan los pasos siguientes para la implementación HoloLens 2 externos:

1. Use la versión [más HoloLens del sistema operativo como](https://aka.ms/hololens2download) compilación de línea de base.
1. Siga estos pasos para asignar licencias basadas en usuario o basadas en dispositivos:
    1. [Cree un grupo en AAD y agregue miembros para](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) HoloLens/RA.
    1. [Asigne licencias basadas en dispositivos o basadas](/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) en el usuario a este grupo.
    1. (Opcional) Grupos de destino para directivas de administración de dispositivos móviles [(MDM).](hololens-enroll-mdm.md)

1. Una los dispositivos de AAD al inquilino, [inscriba automáticamente](/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)y configure a través [de Autopilot](/hololens/hololens2-autopilot). Para más información, consulte propietario [del dispositivo.](/hololens/security-adminless-os#device-owner)
    1. El primer usuario del dispositivo será el propietario del dispositivo.
    1. Si el dispositivo está unido a AAD, el usuario que realizó la unión se hace propietario del dispositivo.
    
1. [El inquilino](/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) bloquea el dispositivo para que solo lo pueda unir el inquilino.
    1. Consulte también CSP [de bloqueo de inquilino.](/windows/client-management/mdm/tenantlockdown-csp)

1. [Configure el modo de pantalla completa mediante el acceso asignado global.](/hololens/hololens-global-assigned-access-kiosk)

1. Deshabilite las siguientes funcionalidades (opcionales):
    1. Capacidad de poner el dispositivo en modo de [desarrollador aquí.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)
    1. La capacidad de conectar el HoloLens a un equipo para copiar la fecha [de deshabilitación de USB.](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)
       > [!NOTE]
        > Si no desea deshabilitar USB, pero desea la capacidad de aplicar un paquete de aprovisionamiento al dispositivo mediante USB, siga las instrucciones sobre cómo permitir la instalación del paquete [de aprovisionamiento](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage).

1. Use [Windows Defender Application Control (WDAC) para](/hololens/windows-defender-application-control-wdac) permitir o bloquear aplicaciones en el HoloLens 2 dispositivo.
1. Actualice Remote Assist a la versión más reciente como parte de la instalación. Tenga en cuenta las dos opciones siguientes:
    1. Vaya a Windows **Microsoft Store --> Remote Assist --> y Actualizar aplicación**.
    1. [ApplicationManagement/AllowAppStoreAutoUpdate,](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) que permite actualizaciones automáticas de aplicaciones, está habilitado de forma predeterminada. Mantenga el dispositivo conectado para recibir actualizaciones.
1. [Deshabilite todas las páginas de](/hololens/settings-uri-list) configuración excepto la configuración de red para permitir que los usuarios se conecten a redes invitadas en sitios cliente.
1. [Administración de actualizaciones de HoloLens](/hololens/hololens-updates)
    1. Opción para [controlar las actualizaciones del sistema operativo](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) o permitir que fluyan libremente.
1. Establezca [restricciones de dispositivo comunes.](/hololens/hololens-common-device-restrictions)

Ahora los clientes externos están listos para usar sus HoloLens 2.

## <a name="common-external-client-deployment-concerns"></a>Problemas comunes de implementación de clientes externos

- [Asegurarse de que los clientes no se pueden comunicar entre sí](#ensure-that-external-clients-cant-communicate-with-one-another)
- [Asegurarse de que los clientes no pueden acceder a los recursos de la empresa](#ensure-that-clients-wont-have-access-to-company-resources)
- [Ocultar o restringir aplicaciones](#hidden-or-restricted-apps)
- [Administración de contraseñas para los clientes](#password-management-for-your-clients) 
- [Asegurarse de que los clientes no pueden acceder al historial de chat](#ensure-that-clients-wont-have-access-to-chat-history)

### <a name="ensure-that-external-clients-cant-communicate-with-one-another"></a>Asegúrese de que los clientes externos no puedan comunicarse entre sí.

Remote Assist HoloLens para HoloLens no se admiten las llamadas. Los clientes pueden buscar, pero no pueden comunicarse entre sí. [Las barreras de información Microsoft 365](/microsoft-365/compliance/information-barriers) pueden restringir aún más con quién un cliente puede buscar y llamar. Otra opción es usar Microsoft Teams [búsqueda de directorios con ámbito.](/MicrosoftTeams/teams-scoped-directory-search)

 > [!NOTE]
> Puesto que el inicio de sesión único está habilitado, es importante deshabilitar el explorador mediante [Windows Defender Application Control (WDAC).](/hololens/windows-defender-application-control-wdac) Si un cliente externo abre el explorador y usa la versión web de Teams, el cliente tendrá acceso al historial de chat.

### <a name="ensure-that-clients-wont-have-access-to-company-resources"></a>Asegúrese de que los clientes no tendrán acceso a los recursos de la empresa.

Hay dos opciones que se deben tener en cuenta.

La primera opción es un enfoque de varias capas:

1. Asigne solo las licencias que requiere el usuario. Si no asigna OneDrive, Outlook, SharePoint, Yammer, etc., el usuario no tendrá acceso a esos recursos. Las únicas licencias que necesitarán los usuarios son Remote Assist, Intune y licencias de AAD para comenzar.
1. Bloquee las aplicaciones (por ejemplo, el correo electrónico) a las que no desea que los clientes accedan (consulte Aplicaciones [ocultas o restringidas).](#apps are hidden or restricted)
1. No comparta nombres de usuario ni contraseñas con los clientes. Para iniciar sesión en el HoloLens 2, se requiere un correo electrónico y un PIN numérico.

La segunda opción es crear un inquilino independiente que hospeda clientes (consulte la imagen 1.1).

**Imagen 1.1**

![Imagen de inquilino de servicio.](./images/hololens-service-tenant-image.png)

### <a name="hidden-or-restricted-apps"></a>Aplicaciones ocultas o restringidas

[El modo de](/hololens/hololens-kiosk) pantalla completa o Windows Defender control de aplicaciones [(WDAC)](/hololens/windows-efender-application-control-wdac) son opciones para ocultar o restringir aplicaciones.

### <a name="password-management-for-your-clients"></a>Administración de contraseñas para los clientes

1. Quite la expiración de la contraseña. Sin embargo, esta opción puede aumentar la posibilidad de que una cuenta se vea comprometida. La recomendación de contraseñas de NIST es cambiar las contraseñas cada 30-90 días.
1. Extienda la expiración de la contraseña HoloLens 2 dispositivos para que superen los 90 días.
1. Los dispositivos deben devolverse a la organización para cambiar las contraseñas. Sin embargo, esta opción puede causar problemas si se espera que los dispositivos estén en la planta del cliente durante más de 90 días.  
1. En el caso de los dispositivos que se envían a varios clientes, restablezca las contraseñas antes de enviar el dispositivo a los clientes.

### <a name="ensure-that-clients-wont-have-access-to-chat-history"></a>Asegurarse de que los clientes no tendrán acceso al historial de chat

Remote Assist borra el historial de chat después de cada sesión. Sin embargo, el historial de chat estará disponible para Microsoft Teams usuarios.

> [!NOTE]
> Puesto que el inicio de sesión único está habilitado, es importante deshabilitar el explorador mediante [Windows Defender Application Control (WDAC).](/hololens/windows-defender-application-control-wdac)  Si un cliente externo abre el explorador y usa la versión web de Teams, el cliente tendrá acceso al historial de llamadas y chat.
