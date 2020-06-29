---
title: Licencias para implementación de realidad mixta
description: ''
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
ms.openlocfilehash: 0da2a2337b3b1f361ffbb698607f304efbf6d193
ms.sourcegitcommit: f3cda6c6b3bfb7ba4be5f4da66d8ed5b03ca807d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830144"
---
# Determinar qué licencias se necesitan

## Guía de licencias de la administración de dispositivos móviles (MDM)

Si tiene previsto administrar sus dispositivos HoloLens, necesitará Azure AD y un MDM. El director activo (AD) no se puede usar para administrar dispositivos HoloLens.
Si tiene previsto usar un MDM que no sea Intune, se necesita una [licencia de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis).
Si tiene previsto usar Intune como MDM, [aquí](https://docs.microsoft.com/intune/fundamentals/licenses) puede ver una lista de conjuntos de aplicaciones que incluyen licencias de Intune. **Tenga en cuenta que Azure AD está incluido en la mayoría de estos conjuntos de aplicaciones.**

## Identificar las licencias necesarias para su escenario y productos

### Requisitos de licencias de HoloLens

Puede que necesite actualizar su dispositivo HoloLens de 1ª generación a Windows Holographic para Business. (vea las [características comerciales de HoloLens](holoLens-commercial-features.md#feature-comparison-between-editions) para decidir si necesita actualizar).

 Si es así, tendrá que hacer lo siguiente:

- Adquirir un archivo XML de licencia de HoloLens Enterprise
- Aplicar el archivo XML a HoloLens. Para ello, puede usar un [paquete de aprovisionamiento](hololens-provisioning.md) o a través del [Administrador de Dispositivos Móviles](https://docs.microsoft.com/intune/configuration/holographic-upgrade)

### Requisitos de licencia de asistencia remota

Asegúrese de que tiene la licencia y el dispositivo necesarios. Puede encontrar los requisitos de licencia y de producto actualizados [aquí](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements).

1. [Licencia de asistencia remota](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist)
1. [Teams Freemium/Teams](https://products.office.com/microsoft-teams/free)
1. [Licencia de Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)

Si tiene previsto implementar **[este escenario entre espacios empresariales](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)**, es posible que necesite una licencia para Barreras de información. Consulte [este artículo](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) para determinar si se requiere una licencia de Barreras de información.

### Requisitos de licencia de guía

Puede encontrar los requisitos de licencia y de dispositivo actualizados [aquí](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements).

1. [Licencia de Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. [Power BI](https://powerbi.microsoft.com/desktop/)
1. [Guías](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup)
