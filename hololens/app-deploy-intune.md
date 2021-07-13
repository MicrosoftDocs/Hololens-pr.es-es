---
title: Intune y Portal de empresa
description: Aprenda a configurar, asignar y crear una experiencia de usuario cómoda con Intune, la administración de dispositivos móviles y el portal de empresa.
keywords: intune, administración de aplicaciones, aplicación, portal de empresa, portal, hololens
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: b192732f5e7edffaa1d0ab081454e4034c416191
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635507"
---
# <a name="intune--company-portal"></a><span data-ttu-id="fd34c-104">Intune y Portal de empresa</span><span class="sxs-lookup"><span data-stu-id="fd34c-104">Intune & Company Portal</span></span>

<span data-ttu-id="fd34c-105">Con Mobile Administración de dispositivos (MDM), puede usar sus propias aplicaciones personalizadas a través de [Microsoft Endpoint Manager (Intune)](/intune/windows-holographic-for-business) para implementarla directamente en los dispositivos HoloLens dispositivos.</span><span class="sxs-lookup"><span data-stu-id="fd34c-105">With Mobile Device Management (MDM), you can use your own custom apps through [Microsoft Endpoint Manager (Intune)](/intune/windows-holographic-for-business) to deploy it directly to your HoloLens devices.</span></span> <span data-ttu-id="fd34c-106">Microsoft Intune es un servicio basado en la nube que se centra en la administración de dispositivos móviles (MDM) y la administración de aplicaciones móviles (MAM).</span><span class="sxs-lookup"><span data-stu-id="fd34c-106">Microsoft Intune is a cloud-based service that focuses on mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="fd34c-107">Intune se incluye en el conjunto de programas de [Enterprise Mobility + Security (EMS)](https://www.microsoft.com/microsoft-365/enterprise-mobility-security) de Microsoft y permite a los usuarios ser productivos manteniendo protegidos los datos de la organización.</span><span class="sxs-lookup"><span data-stu-id="fd34c-107">Intune is included in Microsoft's [Enterprise Mobility + Security (EMS) suite](https://www.microsoft.com/microsoft-365/enterprise-mobility-security), and enables users to be productive while keeping your organization data protected.</span></span> <span data-ttu-id="fd34c-108">Para más información sobre Intune, lea [¿Qué es Intune?](/mem/intune/fundamentals/what-is-intune)</span><span class="sxs-lookup"><span data-stu-id="fd34c-108">To learn more about Intune, read [What is Intune](/mem/intune/fundamentals/what-is-intune).</span></span>

## <a name="setup"></a><span data-ttu-id="fd34c-109">Configurar</span><span class="sxs-lookup"><span data-stu-id="fd34c-109">Setup</span></span>

1. <span data-ttu-id="fd34c-110">Upload una aplicación a una línea de negocio o cargue una aplicación personalizada en el inquilino de Intune.</span><span class="sxs-lookup"><span data-stu-id="fd34c-110">Upload an app to a Line of Business, or upload a custom app to your Intune tenant.</span></span> <span data-ttu-id="fd34c-111">Consulte también: Administración [Enterprise aplicaciones.](/windows/client-management/mdm/enterprise-app-management)</span><span class="sxs-lookup"><span data-stu-id="fd34c-111">See also: [Enterprise app management](/windows/client-management/mdm/enterprise-app-management).</span></span>

2. <span data-ttu-id="fd34c-112">[Asigne la aplicación a un grupo](/mem/intune/apps/apps-deploy).</span><span class="sxs-lookup"><span data-stu-id="fd34c-112">[Assign your app to a group](/mem/intune/apps/apps-deploy).</span></span> <span data-ttu-id="fd34c-113">En función del tipo de asignación que elija, la aplicación se puede entregar automáticamente o disponible para que se pueda retirar fácilmente si tiene una selección de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="fd34c-113">Based on the assignment type you choose, the app can be delivered automatically or available to be readily pulled down if you have a selection of apps.</span></span>

> [!NOTE]
> <span data-ttu-id="fd34c-114">Al compilar la agrupación appx, asegúrese de incluir la arquitectura de los dispositivos en los que va a realizar la implementación.</span><span class="sxs-lookup"><span data-stu-id="fd34c-114">When building your appx bundle make sure to account for including the architecture for the device(s) that you are deploying to.</span></span> <span data-ttu-id="fd34c-115">HoloLens 2 arm64 y HoloLens (1ª generación) es x86.</span><span class="sxs-lookup"><span data-stu-id="fd34c-115">HoloLens 2 is ARM64, and HoloLens (1st Gen) is x86.</span></span> <span data-ttu-id="fd34c-116">Puede incluir ambos en un único paquete appx si planea tener un entorno de dispositivos mixtos.</span><span class="sxs-lookup"><span data-stu-id="fd34c-116">You may include both in a single appx bundle if you plan on having a mixed devices environment.</span></span>

## <a name="assignment-types"></a><span data-ttu-id="fd34c-117">Tipos de asignación</span><span class="sxs-lookup"><span data-stu-id="fd34c-117">Assignment types</span></span>

<span data-ttu-id="fd34c-118">Para que la aplicación se instale automáticamente en el dispositivo después de la inscripción, debe seleccionar **Requerido** para ese grupo.</span><span class="sxs-lookup"><span data-stu-id="fd34c-118">To have your app to be automatically installed on the device after enrollment, you should select **Required** for that group(s).</span></span>
<span data-ttu-id="fd34c-119">Para que la aplicación esté disponible para su descarga en los dispositivos inscritos a través del portal de empresa, **seleccione Disponible para dispositivos inscritos.**</span><span class="sxs-lookup"><span data-stu-id="fd34c-119">To make your app available for download to devices enrolled through the company portal, select **Available for enrolled devices**.</span></span>

## <a name="end-user-experience"></a><span data-ttu-id="fd34c-120">Experiencia del usuario final</span><span class="sxs-lookup"><span data-stu-id="fd34c-120">End-User Experience</span></span>

<span data-ttu-id="fd34c-121">Después de configurar la configuración en Intune, está listo para que los usuarios finales reciban las aplicaciones seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="fd34c-121">After you have set up configuration on Intune, you are ready for end users to receive your selected apps.</span></span>

<span data-ttu-id="fd34c-122">Siga estos pasos para obtener automáticamente las aplicaciones:</span><span class="sxs-lookup"><span data-stu-id="fd34c-122">Follow these steps to automatically get your app(s):</span></span>

1. <span data-ttu-id="fd34c-123">Inscriba el dispositivo con el inquilino.</span><span class="sxs-lookup"><span data-stu-id="fd34c-123">Enroll your device with your tenant.</span></span>
2. <span data-ttu-id="fd34c-124">Una vez que el dispositivo haya completado la inscripción, debe recibir la aplicación en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fd34c-124">Once your device has completed enrollment, you should receive the app on your device.</span></span>
3. <span data-ttu-id="fd34c-125">Si no ve la aplicación inmediatamente, vaya **a Configuración** Accounts Work or School your account Info (Información de la cuenta de trabajo o escuela) y desplácese hacia abajo para ver información sobre el estado de  >    >    >   la aplicación instalada.</span><span class="sxs-lookup"><span data-stu-id="fd34c-125">If you are not seeing you app immediately, go to **Settings** > **Accounts** > **Work or School** > *your account* Info, and scroll down to see information on installed app status.</span></span>

<span data-ttu-id="fd34c-126">Cómo llegar a las aplicaciones a través del Portal de empresa:</span><span class="sxs-lookup"><span data-stu-id="fd34c-126">How to get to apps through the Company Portal:</span></span>

1. <span data-ttu-id="fd34c-127">Abra el **menú Inicio y** seleccione **Microsoft Store**.</span><span class="sxs-lookup"><span data-stu-id="fd34c-127">Open the **Start Menu** and select **Microsoft Store**.</span></span>
2. <span data-ttu-id="fd34c-128">Busque **Portal de empresa** y descargue la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fd34c-128">Search for **Company Portal** and download the app.</span></span>
3. <span data-ttu-id="fd34c-129">Inicie sesión en su cuenta.</span><span class="sxs-lookup"><span data-stu-id="fd34c-129">Sign into your account.</span></span>
4. <span data-ttu-id="fd34c-130">Seleccione la aplicación que desea recibir y descárárelo.</span><span class="sxs-lookup"><span data-stu-id="fd34c-130">Select the app you wish to receive and download it.</span></span>

> [!Tip]
> <span data-ttu-id="fd34c-131">Obtenga más información [sobre la instalación automática de Portal de empresa](/mem/intune/apps/company-portal-app) y la implementación y administración de aplicaciones en [Intune.](/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)</span><span class="sxs-lookup"><span data-stu-id="fd34c-131">Learn more about [auto-installing the Company Portal](/mem/intune/apps/company-portal-app) and [deploying and managing apps in Intune](/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).</span></span>
