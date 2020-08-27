---
title: Requisitos de licencia
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
ms.openlocfilehash: 3ac86512755620ebb6159dd4d845b488e203dbad
ms.sourcegitcommit: 238d41844116ab94d347a2ffd0fbfa18b8a81947
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/24/2020
ms.locfileid: "10956766"
---
# <span data-ttu-id="30696-102">Requisitos de licencia</span><span class="sxs-lookup"><span data-stu-id="30696-102">License requirements</span></span>

## <span data-ttu-id="30696-103">Guía de licencias de la administración de dispositivos móviles (MDM)</span><span class="sxs-lookup"><span data-stu-id="30696-103">Mobile Device Management (MDM) Licenses Guidance</span></span>

<span data-ttu-id="30696-104">Si tiene previsto administrar sus dispositivos HoloLens, necesitará Azure AD y un MDM.</span><span class="sxs-lookup"><span data-stu-id="30696-104">If you plan on managing your HoloLens devices, you will need Azure AD and an MDM.</span></span> <span data-ttu-id="30696-105">El director activo (AD) no se puede usar para administrar dispositivos HoloLens.</span><span class="sxs-lookup"><span data-stu-id="30696-105">Active Director (AD) cannot be used to manage HoloLens devices.</span></span>
<span data-ttu-id="30696-106">Si tiene previsto usar un MDM que no sea Intune, se necesita una [licencia de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis).</span><span class="sxs-lookup"><span data-stu-id="30696-106">If you plan on using an MDM other than Intune, an [Azure Active Directory Licenses](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) is required.</span></span>
<span data-ttu-id="30696-107">Si tiene previsto usar Intune como MDM, [aquí](https://docs.microsoft.com/intune/fundamentals/licenses) puede ver una lista de conjuntos de aplicaciones que incluyen licencias de Intune.</span><span class="sxs-lookup"><span data-stu-id="30696-107">If you plan on using Intune as your MDM,  [here](https://docs.microsoft.com/intune/fundamentals/licenses) are a list of suites that includes Intune licenses.</span></span> **<span data-ttu-id="30696-108">Tenga en cuenta que Azure AD está incluido en la mayoría de estos conjuntos de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="30696-108">Please note that Azure AD is included in the majority of these suites.</span></span>**

## <span data-ttu-id="30696-109">Identificar las licencias necesarias para su escenario y productos</span><span class="sxs-lookup"><span data-stu-id="30696-109">Identify the licenses needed for your scenario and products</span></span>

### <span data-ttu-id="30696-110">Requisitos de licencias de HoloLens (1.ª gen.)</span><span class="sxs-lookup"><span data-stu-id="30696-110">HoloLens (1st gen) Licenses Requirements</span></span>

<span data-ttu-id="30696-111">Puede que necesite actualizar su dispositivo HoloLens de 1.ª generación a Windows Holographic for Business.</span><span class="sxs-lookup"><span data-stu-id="30696-111">You may need to upgrade your HoloLens (1st gen) device to Windows Holographic for Business.</span></span> <span data-ttu-id="30696-112">(vea las [características comerciales de HoloLens](holoLens-commercial-features.md#feature-comparison-between-editions) para decidir si necesita actualizar).</span><span class="sxs-lookup"><span data-stu-id="30696-112">(See [HoloLens commercial features](holoLens-commercial-features.md#feature-comparison-between-editions) to determine if you need to upgrade).</span></span>

 <span data-ttu-id="30696-113">Si es así, tendrá que hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="30696-113">If so, you will need to do the following:</span></span>

- <span data-ttu-id="30696-114">Adquirir un archivo XML de licencia de HoloLens Enterprise</span><span class="sxs-lookup"><span data-stu-id="30696-114">Acquire a HoloLens Enterprise license XML file</span></span>
- <span data-ttu-id="30696-115">Aplicar el archivo XML a HoloLens.</span><span class="sxs-lookup"><span data-stu-id="30696-115">Apply the XML file to the HoloLens.</span></span> <span data-ttu-id="30696-116">Para ello, puede usar un [paquete de aprovisionamiento](hololens-provisioning.md) o a través del [Administrador de Dispositivos Móviles](https://docs.microsoft.com/intune/configuration/holographic-upgrade)</span><span class="sxs-lookup"><span data-stu-id="30696-116">You can do this through a [Provisioning package](hololens-provisioning.md) or through your [Mobile Device Manager](https://docs.microsoft.com/intune/configuration/holographic-upgrade)</span></span>

### <span data-ttu-id="30696-117">Requisitos de licencia de asistencia remota</span><span class="sxs-lookup"><span data-stu-id="30696-117">Remote Assist License Requirements</span></span>

<span data-ttu-id="30696-118">Asegúrese de que tiene la licencia y el dispositivo necesarios.</span><span class="sxs-lookup"><span data-stu-id="30696-118">Make sure you have the required licensing and device.</span></span> <span data-ttu-id="30696-119">Puede encontrar los requisitos de licencia y de producto actualizados [aquí](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements).</span><span class="sxs-lookup"><span data-stu-id="30696-119">Updated licensing and product requirements can be found [here](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements).</span></span>

1. [<span data-ttu-id="30696-120">Licencia de asistencia remota</span><span class="sxs-lookup"><span data-stu-id="30696-120">Remote Assist License</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist)
    1. <span data-ttu-id="30696-121">O use una [Prueba de asistencia remota](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)</span><span class="sxs-lookup"><span data-stu-id="30696-121">Or try a [Remote Assist trial](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)</span></span>
1. [<span data-ttu-id="30696-122">Teams Freemium/Teams</span><span class="sxs-lookup"><span data-stu-id="30696-122">Teams Freemium/Teams</span></span>](https://products.office.com/microsoft-teams/free)
1. [<span data-ttu-id="30696-123">Licencia de Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="30696-123">Azure Active Directory (Azure AD) License</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)

<span data-ttu-id="30696-124">Si tiene previsto implementar **[este escenario entre espacios empresariales](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)**, es posible que necesite una licencia para Barreras de información.</span><span class="sxs-lookup"><span data-stu-id="30696-124">If you plan on implementing **[this cross-tenant scenario](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)**, you may need an Information Barriers license.</span></span> <span data-ttu-id="30696-125">Consulte [este artículo](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) para determinar si se requiere una licencia de Barreras de información.</span><span class="sxs-lookup"><span data-stu-id="30696-125">Please see [this article](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) to determine if an Information Barrier License is required.</span></span>

### <span data-ttu-id="30696-126">Requisitos de licencia de guía</span><span class="sxs-lookup"><span data-stu-id="30696-126">Guides License Requirements</span></span>

<span data-ttu-id="30696-127">Puede encontrar los requisitos de licencia y de dispositivo actualizados [aquí](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements).</span><span class="sxs-lookup"><span data-stu-id="30696-127">Updated licensing and device requirements can be found [here](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements).</span></span>

1. [<span data-ttu-id="30696-128">Licencia de Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="30696-128">Azure Active Directory (Azure AD) License</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. [<span data-ttu-id="30696-129">Power BI</span><span class="sxs-lookup"><span data-stu-id="30696-129">Power BI</span></span>](https://powerbi.microsoft.com/desktop/)
1. [<span data-ttu-id="30696-130">Guías</span><span class="sxs-lookup"><span data-stu-id="30696-130">Guides</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup)
