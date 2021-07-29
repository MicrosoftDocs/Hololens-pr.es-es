---
title: Requisitos de licencia
description: Manténgase al día de todos los requisitos y directrices de licencia que necesita para la administración de dispositivos móviles, HoloLens y Asistencia remota.
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
audience: HoloLens
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
manager: bradke
appliesto:
- HoloLens 2
ms.openlocfilehash: bd7a7d03c81dced4fb66d8ebb176887811e823c9
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640292"
---
# <a name="license-requirements"></a>Requisitos de licencia

## <a name="hololens-2-device-managed"></a>Dispositivo HoloLens 2 (administrado)

[Cuenta de Azure AD](/azure/active-directory/)

> [!IMPORTANT]
> Active Directory (AD) no se puede usar para administrar dispositivos HoloLens.

[Microsoft Intune](/mem/intune/fundamentals/what-is-intune) u otra solución de MDM.
- [Windows Autopilot para HoloLens 2](hololens2-autopilot.md): simplifica la experiencia de aprovisionamiento tanto para los administradores de TI como para los usuarios finales. Los administradores de TI pueden preconfigurar las directivas de HoloLens 2 y, tras el primer arranque, los dispositivos se implementarán listos para los negocios sin interacción del usuario final. 

  > [!NOTE]
  > Windows Autopilot requiere que [Azure P1](/azure/active-directory/fundamentals/active-directory-whatis) y la [inscripción automática](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment) se configuren primero para la implementación de dispositivos y el flujo de Autopilot casi automático. 

### <a name="business-use-case"></a>Caso de uso empresarial: 

- [Escenario de implementación A](hololens-requirements.md#scenario-a-deploy-to-cloud-connected-devices): prueba de concepto o implementación piloto.

- [Escenario de implementación B](hololens-requirements.md#scenario-b-deploy-inside-your-organizations-network): implementación a escala.

## <a name="hololens-2-device-only-non-managed"></a>Solo dispositivo HoloLens 2 (no administrado)

Cuando se usa una cuenta Microsoft (MSA) o una cuenta local, no se requieren licencias adicionales para estas cuentas.

[Cuenta local](/windows/security/identity-protection/access-control/local-accounts)

- Esta cuenta debe [aprovisionarse](hololens-provisioning.md#provisioning-package-hololens-wizard) con antelación mediante el Diseñador de configuración de Windows (WCD).

[Cuenta de Microsoft (MSA)](/windows/security/identity-protection/access-control/microsoft-accounts)

> [!WARNING]
> No se admiten varios usuarios para un dispositivo que usa alguna de estas cuentas.

### <a name="business-use-case"></a>Caso de uso empresarial: 

- [Escenario de implementación C](hololens-requirements.md#scenario-c-deploy-in-secure-offline-environment): implementación sin conexión o segura.
 
## <a name="dynamics-365-licensing-and-requirements"></a>Requisitos y licencias de Dynamics 365

### <a name="dynamics-365-remote-assist"></a>Dynamics 365 Remote Assist 

#### <a name="admin"></a>Administración

- Cuenta de Azure AD (necesaria para comprar la suscripción y asignar licencias)
- [Suscripción a Remote Assist](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (o [prueba de Remote Assist](/dynamics365/mixed-reality/remote-assist/try-remote-assist))
    
#### <a name="dynamics-365-remote-assist-user"></a>Usuario de Dynamics 365 Remote Assist

- Cuenta de Azure AD

- Licencia de Remote Assist 

  > [!NOTE]
  > Microsoft Teams se incluye con Remote Assist.

- Conectividad de red

#### <a name="microsoft-teams-user"></a>Usuario de Microsoft Teams

- Cuenta de Azure AD

- Microsoft Teams o [Teams Freemium](https://products.office.com/microsoft-teams/free).

- Conectividad de red

Si planea implementar este [escenario entre inquilinos](/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants), puede que necesite una licencia de Barreras a la información. Consulte [este artículo](/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) para determinar si se requiere una licencia de Barreras a la información.

### <a name="dynamics-365-guides"></a>Dynamics 365 Guides 

#### <a name="admin"></a>Administración

- Cuenta de Azure AD (necesaria para comprar la suscripción y asignar licencias)
- [Suscripción o prueba gratuita de Dynamics 365 Guides](/dynamics365/mixed-reality/guides/setup-step-one)

#### <a name="guides-author"></a>Autor de Guides

1. Cuenta de Azure AD
1. [Licencia de Dynamics 365 Guides](/dynamics365/mixed-reality/guides/requirements)
1. Aplicación Dynamics 365 Guides instalada en un equipo o un dispositivo HoloLens
1. [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (se usa para ver el panel de Analytics)
1. Rol de autor (para crear guías)
1. Conectividad de red

#### <a name="guides-user"></a>Usuario de Guides

1. Cuenta de Azure AD
1. [Licencia de Dynamics 365 Guides](/dynamics365/mixed-reality/guides/requirements)
1. Aplicación Dynamics 365 Guides instalada en un dispositivo HoloLens
1. Rol de operador (para probar o usar guías)
1. Conectividad de red
