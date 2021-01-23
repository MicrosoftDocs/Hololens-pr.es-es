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
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2f7af532d2172dcaa6514ee11dbb0d6ab5631929
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283971"
---
# Requisitos de licencia

## Guía de licencias de la administración de dispositivos móviles (MDM)

Si tiene previsto administrar sus dispositivos HoloLens, necesitará Azure AD y un MDM. El director activo (AD) no se puede usar para administrar dispositivos HoloLens.
Si tiene previsto usar un MDM que no sea Intune, necesitará una [licencia de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis).
Si tiene previsto usar Intune como MDM, lea la [lista de conjuntos](https://docs.microsoft.com/intune/fundamentals/licenses) de aplicaciones que incluyen licencias de Intune. **Tenga en cuenta que Azure AD está incluido en la mayoría de estos conjuntos de aplicaciones.**

## Identificar las licencias necesarias para su escenario y productos

### Requisitos de licencias de HoloLens (1.ª gen.)

Puede que necesite actualizar su dispositivo HoloLens de 1.ª generación a Windows Holographic for Business. (vea las [características comerciales de HoloLens](holoLens-commercial-features.md#feature-comparison-between-editions) para decidir si necesita actualizar).

 Si es así, tendrá que hacer lo siguiente:

- Adquirir un archivo XML de licencia de HoloLens Enterprise
- Aplicar el archivo XML a HoloLens. Para ello, puede usar un [paquete de aprovisionamiento](hololens-provisioning.md) o a través del [Administrador de Dispositivos Móviles](https://docs.microsoft.com/intune/configuration/holographic-upgrade)

### Requisitos de licencia de asistencia remota

Asegúrese de que tiene la licencia y el dispositivo necesarios. Puede comprobarlo en la documentación de [requisitos](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements).

1. [Licencia de asistencia remota](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist)
    1. O use una [Prueba de asistencia remota](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)
1. [Teams Freemium/Teams](https://products.office.com/microsoft-teams/free)
1. [Licencia de Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)

Si tiene previsto implementar **[este escenario entre espacios empresariales](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)**, es posible que necesite una licencia para Barreras de información. Consulte [este artículo](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) para determinar si se requiere una licencia de Barreras de información.

### Requisitos de licencia de guía

Consulte los [requisitos actualizados de licencias y dispositivos](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements).

1. [Licencia de Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. [Power BI](https://powerbi.microsoft.com/desktop/)
1. [Guías](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup)
