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
ms.openlocfilehash: aae4e1dbbf28906c1f93ac7f29620260023f596bb96fc23a3ee78442e70585fa
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "115663297"
---
# <a name="license-requirements"></a>Requisitos de licencia

## <a name="overview"></a>Introducción
En esta página se proporciona información general de alto nivel de las licencias y las cuentas necesarias para implementar dispositivos de HoloLens 2 administrados y no administrados en su organización. También se incluye información sobre las licencias de Dynamics 365 [Remote Assist](#dynamics-365-remote-assist) y [Guides](#dynamics-365-guides).

## <a name="hololens-2-license-and-account-requirements"></a>Requisitos de las cuentas y licencias de HoloLens 2

 
|       &nbsp;      | Dispositivos HoloLens administrados | Dispositivos HoloLens no administrados |
|-------------------|-----------------|---------------------|
| **Caso de uso empresarial** | | |
| [Implementación en dispositivos conectados a la nube: prueba de concepto/implementación piloto](hololens-requirements.md#scenario-a-deploy-to-cloud-connected-devices)  | ✔️| |
| [Implementación dentro de la red de la organización: implementación a gran escala](hololens-requirements.md#scenario-b-deploy-inside-your-organizations-network) | ✔️| |
| [Implementación en un entorno sin conexión seguro](hololens-requirements.md#scenario-c-deploy-in-secure-offline-environment) | | ✔️ |
| **Licencias** | | |
| Azure Active Directory | ✔️ | |
| MDM (Intune<sup>1</sup> o <sup>2</sup>) | ✔️  | |
| **Cuentas** |  | |
| Cuenta de administrador de Azure AD | ✔️ |  |
| Cuenta de usuario de Azure AD | ✔️ | |
| [Cuenta de Microsoft (MSA)](/windows/security/identity-protection/access-control/microsoft-accounts)| | ✔️ |
| [Cuenta local](/windows/security/identity-protection/access-control/local-accounts)<sup>3</sup> | | ✔️ |
- <sup>1</sup> [Inscripción automática](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment) durante la configuración inicial del dispositivo, que se registra y se une a Azure Active Directory y permite que el dispositivo se administre con Intune.
- <sup>2</sup> [Windows Autopilot para HoloLens 2](hololens2-autopilot.md) simplifica la experiencia de aprovisionamiento tanto para los administradores de TI como para los usuarios finales. Los administradores de TI pueden preconfigurar las directivas de HoloLens 2 y, tras el primer arranque, los dispositivos se implementarán listos para los negocios sin interacción del usuario final.
- <sup>3</sup> Esta cuenta debe [aprovisionarse](hololens-provisioning.md#provisioning-package-hololens-wizard) con antelación mediante el Diseñador de configuración de Windows (WCD).

> [!IMPORTANT]
> Active Directory (AD) no se puede usar para administrar dispositivos HoloLens.
 
> [!WARNING]
> No se admiten varios usuarios para un dispositivo que usa una cuenta local o MSA.

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

- Microsoft Teams o [Teams Freemium](https://products.office.com/microsoft-teams/free)

- Conectividad de red

Si planea implementar este [escenario entre inquilinos](/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants), puede que necesite una licencia de Barreras a la información. Consulte [este artículo](/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) para determinar si se requiere una licencia de Barreras a la información.

### <a name="dynamics-365-guides"></a>Dynamics 365 Guides 

#### <a name="admin"></a>Administración

1. Cuenta de Azure AD (necesaria para comprar la suscripción y asignar licencias)
2. [Suscripción o prueba gratuita de Dynamics 365 Guides](/dynamics365/mixed-reality/guides/setup-step-one)

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
