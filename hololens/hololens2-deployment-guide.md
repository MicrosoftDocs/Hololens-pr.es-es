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
ms.openlocfilehash: 56930ceea05cd5713b9c7eb57e0967a9d0cd4988
ms.sourcegitcommit: fbc8ddb17e31fea8667ece43a511592b86ac3947
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "11385584"
---
# <a name="deploying-hololens-2-to-external-clients-with-remote-assist"></a>Implementar HoloLens 2 en clientes externos con asistencia remota

Esta guía ayuda a los profesionales de IT con los siguientes objetivos a implementar dispositivos de Microsoft HoloLens 2 en su organización:

1. Dispositivos HoloLens 2 de conexión en la nube
1. Prestar dispositivos HoloLens 2 a clientes externos para su uso
1. Dispositivos prestados seguros

Esta guía proporcionará recomendaciones generales de implementación de [HoloLens 2](#general-deployment-recommendations-and-instructions) que se [](#common-concerns) aplican a la mayoría de los escenarios de implementación de HoloLens 2 y a las preocupaciones comunes que tienen los clientes al implementar asistencia remota para uso externo.

## <a name="scenario-description"></a>Descripción del escenario

Para este documento, contoso Company quiere enviar un dispositivo HoloLens 2 a la planta de un cliente externo para su uso a corto o largo plazo. Cuando el cliente necesita asistencia para el mantenimiento de la máquina, el cliente inicia sesión en el dispositivo HoloLens 2 con las credenciales proporcionadas por la compañía Contoso y usa asistencia remota para ponerse en contacto con los expertos de la compañía Contoso.

Obtenga más información sobre asistencia remota [aquí](https://docs.microsoft.com/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist).

### <a name="requirements-for-this-scenario"></a>Requisitos para este escenario

1. [Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. Administrador de dispositivos móviles, como [Intune](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)
1. Licencia de asistencia remota
    1. [Comprar asistencia remota](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
    1. [Asistencia remota de prueba](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)

## <a name="common-concerns"></a>Preocupaciones comunes

- [Cómo asegurarse de que los clientes externos no tienen la capacidad de comunicarse entre sí](#how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another)
- [Cómo asegurarse de que los clientes no tienen acceso a los recursos de la empresa](#how-to-ensure-that-clients-do-not-have-access-to-company-resources)
- [Cómo restringir aplicaciones](#how-to-restrict-apps)
- [Cómo administrar contraseñas](#how-to-manage-passwords)
- [Cómo asegurarse de que los clientes no tienen acceso al historial de chat](#how-to-ensure-that-clients-do-not-have-access-to-chat-history)

### <a name="how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another"></a>Cómo asegurarse de que los clientes externos no tienen la capacidad de comunicarse entre sí

Dado que las llamadas de HoloLens de asistencia remota a HoloLens no son compatibles, los clientes pueden buscar, pero no pueden comunicarse entre sí. Para restringir aún más a quién pueden buscar y llamar los clientes, las  [barreras](https://docs.microsoft.com/microsoft-365/compliance/information-barriers?view=o365-worldwide) de información pueden restringir con quién se puede comunicar un cliente. Otra opción a tener en cuenta es usar [la búsqueda de directorios con ámbito](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search)

 > [!NOTE]
> Dado que el inicio de sesión único está habilitado, es importante deshabilitar el explorador mediante [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac). Si un cliente externo abre el explorador y usa la versión web de Teams, el cliente tendrá acceso al historial de llamadas y chat.

### <a name="how-to-ensure-that-clients-do-not-have-access-to-company-resources"></a>Cómo asegurarse de que los clientes no tienen acceso a los recursos de la empresa

Hay dos opciones a tener en cuenta.

La primera opción es un enfoque de varias capas:

1. Solo asigne licencias que el usuario requiera. Si no asigna OneDrive, Outlook, SharePoint, Yammer, etc. al usuario, no tendrá acceso a esos recursos. Las únicas licencias que necesitarán los usuarios son las licencias de Asistencia remota, Intune y AAD para comenzar.
1. Bloquear aplicaciones (como el correo electrónico) a las que no quieres que los clientes accedan (consulta [Cómo restringir aplicaciones).](#how-to-restrict-apps)
1. NO comparta nombres de usuario ni contraseña con clientes. Para iniciar sesión en HoloLens 2, se requiere un PIN numérico y de correo electrónico.

La segunda opción es crear un inquilino independiente que hospeda clientes (vea la imagen 1.1).

**Imagen 1.1**

![Imagen del inquilino del servicio](./images/hololens-service-tenant-image.png)

### <a name="how-to-restrict-apps"></a>Cómo restringir aplicaciones

[El Modo de](https://docs.microsoft.com/hololens/hololens-kiosk) pantalla completa o [WDAC (Windows Defender control](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) de aplicaciones) son opciones para restringir aplicaciones.

### <a name="how-to-manage-passwords"></a>Cómo administrar contraseñas

1. Quitar la expiración de contraseña. Sin embargo, esto aumenta la posibilidad de que una cuenta se vea comprometida. La recomendación de contraseña de NIST es cambiar las contraseñas cada 30-90 días.
1. Extender la expiración de contraseña para dispositivos HoloLens 2 para que supere los 90 días.
1. Los dispositivos deben devolverse a Contoso para cambiar las contraseñas. Sin embargo, esto puede causar problemas si se espera que los dispositivos estén en la planta del cliente durante más de 90 días.  
1. Para los dispositivos que se envían a varios clientes, restablezca las contraseñas antes de enviar el dispositivo a los clientes.

### <a name="how-to-ensure-that-clients-do-not-have-access-to-chat-history"></a>Cómo asegurarse de que los clientes no tienen acceso al historial de chat

Asistencia remota borra el historial de chat después de cada sesión. Sin embargo, el historial de chat estará disponible para el usuario de Microsoft Teams.

> [!NOTE]
> Dado que el inicio de sesión único está habilitado, es importante deshabilitar el explorador mediante [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac). Si un cliente externo abre el explorador y usa la versión web de Teams, el cliente tendrá acceso al historial de llamadas y chat.

## <a name="general-deployment-recommendations-and-instructions"></a>Recomendaciones e instrucciones de implementación general

Se recomienda lo siguiente para los pasos de implementación de HoloLens 2:

1. Usa la [versión más reciente del sistema operativo HoloLens](https://aka.ms/hololens2download) como compilación de línea base.
1. Asignar licencias basadas en el usuario o basadas en dispositivos:
    1. Tanto las licencias basadas en el usuario como las licencias basadas en dispositivos siguen los siguientes pasos:
        1. [Cree un grupo en AAD y agregue miembros para](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) usuarios de HoloLens/RA.
        1. [Asigne licencias basadas](https://docs.microsoft.com/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) en dispositivos o basadas en usuario a este grupo.
        1. (Opcional) Puedes dirigirte a grupos para directivas MDM.

1. Los dispositivos deben estar unidos a AAD al [inquilino,](https://docs.microsoft.com/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)inscribirse automáticamente y configurarse a través del [piloto automático.](https://docs.microsoft.com/hololens/hololens2-autopilot)
    1. Ten en cuenta que el primer usuario del dispositivo será el propietario del dispositivo.
    1. Ten en cuenta que si el dispositivo está unido a AAD, el usuario que realizó la unión se hace propietario del dispositivo.
    1. Para obtener más información, consulta [Propietario del dispositivo](https://docs.microsoft.com/hololens/security-adminless-os#device-owner).
1. [El inquilino bloquea](https://docs.microsoft.com/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) el dispositivo para que solo pueda unirse a tu espacio empresarial.
    1. **Vínculo adicional: CSP** [de bloqueo de inquilino](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp).
1. Configure kiosk using global assigned access to [here](https://docs.microsoft.com/hololens/hololens-global-assigned-access-kiosk).
1. Se recomienda deshabilitar las siguientes funcionalidades (opcionales):
    1. Capacidad para poner el dispositivo en modo de desarrollador [aquí](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock).
    1. Capacidad de conectar HoloLens a un equipo para copiar la fecha [deshabilitar USB](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection).
       > [!NOTE]
        > Si no quieres deshabilitar USB pero quieres la posibilidad de aplicar un paquete de aprovisionamiento al dispositivo mediante USB, sigue las instrucciones que se indican [**aquí.**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)

1. Usa [WDAC](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) para permitir o bloquear aplicaciones en el dispositivo HoloLens 2.
1. Actualice asistencia remota a la versión más reciente como parte de la instalación. Hay dos opciones para hacerlo:
    1. Para ello, vaya a Windows **Microsoft Store --> Remote Assist --> y Update App**.
    1. [ApplicationManagement/AllowAppStoreAutoUpdate,](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) que permite actualizaciones automáticas de aplicaciones, está habilitada de forma predeterminada. Mantén el dispositivo conectado para recibir actualizaciones.
1. [Deshabilite todas](https://docs.microsoft.com/hololens/settings-uri-list) las páginas de configuración excepto la configuración de red para permitir que los usuarios se conecten a redes invitadas en sitios cliente.
1. [Administrar actualizaciones de HoloLens](https://docs.microsoft.com/hololens/hololens-updates)
    1. Opción para [controlar las actualizaciones del sistema](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) operativo o permitir que fluya libremente.
1. [Restricciones comunes de dispositivos](https://docs.microsoft.com/hololens/hololens-common-device-restrictions).
