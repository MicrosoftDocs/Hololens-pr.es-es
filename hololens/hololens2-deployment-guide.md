---
title: Guía de implementación de clientes externos
description: Guía de implementación HoloLens 2 para clientes externos (con asistencia remota como ejemplo)
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
ms.openlocfilehash: 495be858c235931ed591b097e6b5951f7197c3f7a62bd1aaa16bea65a4e3885f
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "115659893"
---
# <a name="deploying-hololens-2-to-external-clients-with-remote-assist"></a>Implementación de HoloLens 2 en clientes externos con Remote Assist

Esta guía ayuda a los profesionales de IT con los siguientes objetivos a implementar Microsoft HoloLens 2 dispositivos de su organización:

1. Dispositivos de conexión HoloLens 2 nube
1. Prestar HoloLens 2 dispositivos a clientes externos para su uso
1. Proteger dispositivos cedido

En esta guía se proporcionan recomendaciones [de implementación](#general-deployment-recommendations-and-instructions) HoloLens 2 generales que se [](#common-concerns) aplican HoloLens 2 la mayoría de los escenarios de implementación de HoloLens 2 y problemas comunes que tienen los clientes al implementar Remote Assist para uso externo.

## <a name="scenario-description"></a>Descripción del escenario

Para este documento, contoso Company quiere enviar un dispositivo HoloLens 2 a la planta de un cliente externo para su uso a corto o largo plazo. Cuando el cliente necesita asistencia para el mantenimiento de la maquinaria, el cliente inicia sesión en el dispositivo HoloLens 2 con las credenciales proporcionadas por contoso Company y usa Remote Assist para ponerse en contacto con los expertos de contoso Company.

Obtenga más información sobre Remote Assist [aquí.](/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist)

### <a name="requirements-for-this-scenario"></a>Requisitos para este escenario

1. [Azure AD](/azure/active-directory/fundamentals/active-directory-whatis)
1. Dispositivos Administrador de dispositivos móviles, como [Intune](/mem/intune/fundamentals/free-trial-sign-up)
1. Remote Assist licencia
    1. [Comprar Remote Assist](/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
    1. [Versión de Remote Assist](/dynamics365/mixed-reality/remote-assist/try-remote-assist)

## <a name="common-concerns"></a>Problemas comunes

- [Cómo asegurarse de que los clientes externos no tienen la capacidad de comunicarse entre sí](#how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another)
- [Cómo asegurarse de que los clientes no tienen acceso a los recursos de la empresa](#how-to-ensure-that-clients-do-not-have-access-to-company-resources)
- [Cómo restringir aplicaciones](#how-to-restrict-apps)
- [Administración de contraseñas](#how-to-manage-passwords)
- [Cómo asegurarse de que los clientes no tienen acceso al historial de chat](#how-to-ensure-that-clients-do-not-have-access-to-chat-history)

### <a name="how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another"></a>Cómo asegurarse de que los clientes externos no tienen la capacidad de comunicarse entre sí

Dado Remote Assist HoloLens no HoloLens las llamadas, los clientes pueden buscar, pero no pueden, comunicarse entre sí. Para restringir aún más los clientes que pueden buscar y llamar a ,  [las barreras de información](/microsoft-365/compliance/information-barriers) pueden restringir con quién puede comunicarse un cliente. Otra opción a tener en cuenta es usar [la búsqueda de directorios con ámbito](/MicrosoftTeams/teams-scoped-directory-search)

 > [!NOTE]
> Puesto que el inicio de sesión único está habilitado, es importante deshabilitar el explorador mediante [**WDAC.**](/hololens/windows-defender-application-control-wdac) Si un cliente externo abre el explorador y usa la versión web de Teams, el cliente tendrá acceso al historial de llamadas y chat.

### <a name="how-to-ensure-that-clients-do-not-have-access-to-company-resources"></a>Cómo asegurarse de que los clientes no tienen acceso a los recursos de la empresa

Hay dos opciones que se deben tener en cuenta.

La primera opción es un enfoque de varias capas:

1. Asigne solo las licencias que requiera el usuario. Si no asigna OneDrive, Outlook, SharePoint, Yammer, etc., al usuario, no tendrá acceso a esos recursos. Las únicas licencias que necesitarán los usuarios Remote Assist, Intune y AAD para comenzar.
1. Bloquee las aplicaciones (por ejemplo, el correo electrónico) a las que no desea que los clientes accedan (consulte [Cómo restringir aplicaciones).](#how-to-restrict-apps)
1. NO comparta nombres de usuario ni contraseñas con los clientes. Para iniciar sesión en el HoloLens 2, se requiere un correo electrónico y un PIN numérico.

La segunda opción es crear un inquilino independiente que hospeda clientes (consulte la imagen 1.1).

**Imagen 1.1**

![Imagen de inquilino de servicio](./images/hololens-service-tenant-image.png)

### <a name="how-to-restrict-apps"></a>Cómo restringir aplicaciones

[El modo de](/hololens/hololens-kiosk) pantalla completa o [WDAC (Windows Defender Application Control)](/hololens/windows-defender-application-control-wdac) son opciones para restringir las aplicaciones.

### <a name="how-to-manage-passwords"></a>Administración de contraseñas

1. Quite la expiración de la contraseña. Sin embargo, esto aumenta la posibilidad de que una cuenta se vea comprometida. La recomendación de contraseña de NIST es cambiar las contraseñas cada 30-90 días.
1. Amplíe la expiración de la contraseña para HoloLens 2 dispositivos que superen los 90 días.
1. Los dispositivos deben devolverse a Contoso para cambiar las contraseñas. Sin embargo, esto puede causar problemas si se espera que los dispositivos estén en la planta del cliente durante más de 90 días.  
1. En el caso de los dispositivos que se envían a varios clientes, restablezca las contraseñas antes de enviar el dispositivo a los clientes.

### <a name="how-to-ensure-that-clients-do-not-have-access-to-chat-history"></a>Cómo asegurarse de que los clientes no tienen acceso al historial de chat

Remote Assist el historial de chat después de cada sesión. Sin embargo, el historial de chat estará disponible para el Microsoft Teams usuario.

> [!NOTE]
> Puesto que el inicio de sesión único está habilitado, es importante deshabilitar el explorador mediante [**WDAC.**](/hololens/windows-defender-application-control-wdac) Si un cliente externo abre el explorador y usa la versión web de Teams, el cliente tendrá acceso al historial de llamadas y chat.

## <a name="general-deployment-recommendations-and-instructions"></a>Instrucciones y Recomendaciones implementación general

Se recomienda lo siguiente para realizar HoloLens 2 de implementación:

1. Use la versión [más HoloLens del sistema operativo como](https://aka.ms/hololens2download) compilación de línea base.
1. Asignar licencias basadas en usuario o basadas en dispositivos:
    1. Las licencias basadas en usuario y basadas en dispositivos siguen estos pasos:
        1. [Cree un grupo en AAD y agregue miembros para](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) HoloLens/RA.
        1. [Asigne licencias basadas en dispositivos o basadas](/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) en usuarios a este grupo.
        1. (Opcional) Puede establecer como destino grupos para directivas MDM.

1. Los dispositivos deben estar unidos a AAD al inquilino, [inscritos automáticamente](/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)y configurados a través [del piloto automático.](/hololens/hololens2-autopilot)
    1. Tenga en cuenta que el primer usuario del dispositivo será el propietario del dispositivo.
    1. Tenga en cuenta que si el dispositivo está unido a AAD, el usuario que realizó la unión se hace propietario del dispositivo.
    1. Para más información, consulte [Propietario del dispositivo.](/hololens/security-adminless-os#device-owner)
1. [El inquilino](/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) bloquea el dispositivo para que solo pueda unirse al inquilino.
    1. **Vínculo adicional: CSP** [de bloqueo de inquilino.](/windows/client-management/mdm/tenantlockdown-csp)
1. Configure la pantalla completa mediante el acceso global asignado [a aquí.](/hololens/hololens-global-assigned-access-kiosk)
1. Se recomienda deshabilitar las siguientes funcionalidades (opcionales):
    1. Capacidad de poner el dispositivo en modo de desarrollador [aquí.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)
    1. La capacidad de conectar el HoloLens a un equipo para copiar la fecha [de deshabilitación de USB.](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)
       > [!NOTE]
        > Si no desea deshabilitar USB, pero desea la capacidad de aplicar un paquete de aprovisionamiento al dispositivo mediante USB, siga las instrucciones que se indican [**aquí.**](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)

1. Use [WDAC](/hololens/windows-defender-application-control-wdac) para permitir o bloquear aplicaciones en el HoloLens 2 dispositivo.
1. Actualice Remote Assist a la versión más reciente como parte de la instalación. Hay dos opciones para hacerlo:
    1. Para ello, vaya a Windows **Microsoft Store --> Remote Assist --> y Actualizar aplicación**.
    1. [ApplicationManagement/AllowAppStoreAutoUpdate,](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) que permite actualizaciones automáticas de aplicaciones, está habilitado de forma predeterminada. Mantenga el dispositivo conectado para recibir actualizaciones.
1. [Deshabilite todas las páginas de configuración](/hololens/settings-uri-list) excepto la configuración de red para permitir que los usuarios se conecten a redes invitadas en sitios cliente.
1. [Administración de HoloLens actualizaciones](/hololens/hololens-updates)
    1. Opción para [controlar las actualizaciones del sistema](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) operativo o permitir que fluyan libremente.
1. [Restricciones comunes de dispositivos](/hololens/hololens-common-device-restrictions).
