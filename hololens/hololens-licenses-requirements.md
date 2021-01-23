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
# <span data-ttu-id="632e5-103">Requisitos de licencia</span><span class="sxs-lookup"><span data-stu-id="632e5-103">License requirements</span></span>

## <span data-ttu-id="632e5-104">Guía de licencias de la administración de dispositivos móviles (MDM)</span><span class="sxs-lookup"><span data-stu-id="632e5-104">Mobile Device Management (MDM) Licenses Guidance</span></span>

<span data-ttu-id="632e5-105">Si tiene previsto administrar sus dispositivos HoloLens, necesitará Azure AD y un MDM.</span><span class="sxs-lookup"><span data-stu-id="632e5-105">If you plan on managing your HoloLens devices, you will need Azure AD and an MDM.</span></span> <span data-ttu-id="632e5-106">El director activo (AD) no se puede usar para administrar dispositivos HoloLens.</span><span class="sxs-lookup"><span data-stu-id="632e5-106">Active Director (AD) cannot be used to manage HoloLens devices.</span></span>
<span data-ttu-id="632e5-107">Si tiene previsto usar un MDM que no sea Intune, necesitará una [licencia de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis).</span><span class="sxs-lookup"><span data-stu-id="632e5-107">If you plan on using an MDM other than Intune, an [Azure Active Directory Licenses](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) is required.</span></span>
<span data-ttu-id="632e5-108">Si tiene previsto usar Intune como MDM, lea la [lista de conjuntos](https://docs.microsoft.com/intune/fundamentals/licenses) de aplicaciones que incluyen licencias de Intune.</span><span class="sxs-lookup"><span data-stu-id="632e5-108">If you plan on using Intune as your MDM, read up on the [list of suites](https://docs.microsoft.com/intune/fundamentals/licenses) that include Intune licenses.</span></span> **<span data-ttu-id="632e5-109">Tenga en cuenta que Azure AD está incluido en la mayoría de estos conjuntos de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="632e5-109">Please note that Azure AD is included in the majority of these suites.</span></span>**

## <span data-ttu-id="632e5-110">Identificar las licencias necesarias para su escenario y productos</span><span class="sxs-lookup"><span data-stu-id="632e5-110">Identify the licenses needed for your scenario and products</span></span>

### <span data-ttu-id="632e5-111">Requisitos de licencias de HoloLens (1.ª gen.)</span><span class="sxs-lookup"><span data-stu-id="632e5-111">HoloLens (1st gen) Licenses Requirements</span></span>

<span data-ttu-id="632e5-112">Puede que necesite actualizar su dispositivo HoloLens de 1.ª generación a Windows Holographic for Business.</span><span class="sxs-lookup"><span data-stu-id="632e5-112">You may need to upgrade your HoloLens (1st gen) device to Windows Holographic for Business.</span></span> <span data-ttu-id="632e5-113">(vea las [características comerciales de HoloLens](holoLens-commercial-features.md#feature-comparison-between-editions) para decidir si necesita actualizar).</span><span class="sxs-lookup"><span data-stu-id="632e5-113">(See [HoloLens commercial features](holoLens-commercial-features.md#feature-comparison-between-editions) to determine if you need to upgrade).</span></span>

 <span data-ttu-id="632e5-114">Si es así, tendrá que hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="632e5-114">If so, you will need to do the following:</span></span>

- <span data-ttu-id="632e5-115">Adquirir un archivo XML de licencia de HoloLens Enterprise</span><span class="sxs-lookup"><span data-stu-id="632e5-115">Acquire a HoloLens Enterprise license XML file</span></span>
- <span data-ttu-id="632e5-116">Aplicar el archivo XML a HoloLens.</span><span class="sxs-lookup"><span data-stu-id="632e5-116">Apply the XML file to the HoloLens.</span></span> <span data-ttu-id="632e5-117">Para ello, puede usar un [paquete de aprovisionamiento](hololens-provisioning.md) o a través del [Administrador de Dispositivos Móviles](https://docs.microsoft.com/intune/configuration/holographic-upgrade)</span><span class="sxs-lookup"><span data-stu-id="632e5-117">You can do this through a [Provisioning package](hololens-provisioning.md) or through your [Mobile Device Manager](https://docs.microsoft.com/intune/configuration/holographic-upgrade)</span></span>

### <span data-ttu-id="632e5-118">Requisitos de licencia de asistencia remota</span><span class="sxs-lookup"><span data-stu-id="632e5-118">Remote Assist License Requirements</span></span>

<span data-ttu-id="632e5-119">Asegúrese de que tiene la licencia y el dispositivo necesarios. Puede comprobarlo en la documentación de [requisitos](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements).</span><span class="sxs-lookup"><span data-stu-id="632e5-119">Make sure you have the required licensing and device, which you can check in the [requirements](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements) documentation.</span></span>

1. [<span data-ttu-id="632e5-120">Licencia de asistencia remota</span><span class="sxs-lookup"><span data-stu-id="632e5-120">Remote Assist License</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist)
    1. <span data-ttu-id="632e5-121">O use una [Prueba de asistencia remota](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)</span><span class="sxs-lookup"><span data-stu-id="632e5-121">Or try a [Remote Assist trial](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)</span></span>
1. [<span data-ttu-id="632e5-122">Teams Freemium/Teams</span><span class="sxs-lookup"><span data-stu-id="632e5-122">Teams Freemium/Teams</span></span>](https://products.office.com/microsoft-teams/free)
1. [<span data-ttu-id="632e5-123">Licencia de Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="632e5-123">Azure Active Directory (Azure AD) License</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)

<span data-ttu-id="632e5-124">Si tiene previsto implementar **[este escenario entre espacios empresariales](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)**, es posible que necesite una licencia para Barreras de información.</span><span class="sxs-lookup"><span data-stu-id="632e5-124">If you plan on implementing **[this cross-tenant scenario](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)**, you may need an Information Barriers license.</span></span> <span data-ttu-id="632e5-125">Consulte [este artículo](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) para determinar si se requiere una licencia de Barreras de información.</span><span class="sxs-lookup"><span data-stu-id="632e5-125">Please see [this article](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) to determine if an Information Barrier License is required.</span></span>

### <span data-ttu-id="632e5-126">Requisitos de licencia de guía</span><span class="sxs-lookup"><span data-stu-id="632e5-126">Guides License Requirements</span></span>

<span data-ttu-id="632e5-127">Consulte los [requisitos actualizados de licencias y dispositivos](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements).</span><span class="sxs-lookup"><span data-stu-id="632e5-127">Check out the [updated licensing and device requirements](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements).</span></span>

1. [<span data-ttu-id="632e5-128">Licencia de Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="632e5-128">Azure Active Directory (Azure AD) License</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. [<span data-ttu-id="632e5-129">Power BI</span><span class="sxs-lookup"><span data-stu-id="632e5-129">Power BI</span></span>](https://powerbi.microsoft.com/desktop/)
1. [<span data-ttu-id="632e5-130">Guías</span><span class="sxs-lookup"><span data-stu-id="632e5-130">Guides</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup)
