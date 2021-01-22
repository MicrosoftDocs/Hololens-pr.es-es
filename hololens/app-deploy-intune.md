---
title: Intune y portal de empresa
description: Obtenga información sobre cómo configurar, asignar y crear una experiencia de usuario cómoda con Intune, la administración de dispositivos móviles y el portal de la empresa.
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
ms.openlocfilehash: f91f97b6cddf678b20d0bdb3f381e01809b10f3f
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283721"
---
# <span data-ttu-id="965b8-104">Portal de empresa e Intune</span><span class="sxs-lookup"><span data-stu-id="965b8-104">Intune & Company Portal</span></span>

<span data-ttu-id="965b8-105">Con administración de dispositivos móviles (MDM), puedes usar tus propias aplicaciones personalizadas a través de [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) para implementarla directamente en los dispositivos HoloLens.</span><span class="sxs-lookup"><span data-stu-id="965b8-105">With Mobile Device Management (MDM), you can use your own custom apps through [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) to deploy it directly to your HoloLens devices.</span></span> <span data-ttu-id="965b8-106">Microsoft Intune es un servicio basado en la nube que se centra en la administración de dispositivos móviles (MDM) y la administración de aplicaciones móviles (MAM).</span><span class="sxs-lookup"><span data-stu-id="965b8-106">Microsoft Intune is a cloud-based service that focuses on mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="965b8-107">Intune se incluye en el conjunto de aplicaciones [Enterprise Mobility + Security (EMS)](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)de Microsoft y permite a los usuarios ser productivos mientras mantienen protegidos los datos de su organización.</span><span class="sxs-lookup"><span data-stu-id="965b8-107">Intune is included in Microsoft's [Enterprise Mobility + Security (EMS) suite](https://www.microsoft.com/microsoft-365/enterprise-mobility-security), and enables users to be productive while keeping your organization data protected.</span></span> <span data-ttu-id="965b8-108">Para obtener más información sobre Intune, lea [¿Qué es Intune?](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)</span><span class="sxs-lookup"><span data-stu-id="965b8-108">To learn more about Intune, read [What is Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune).</span></span>

## <span data-ttu-id="965b8-109">Programa de instalación</span><span class="sxs-lookup"><span data-stu-id="965b8-109">Setup</span></span>

1. <span data-ttu-id="965b8-110">Cargue una aplicación en una línea de negocio o cargue una aplicación personalizada en su inquilino de Intune.</span><span class="sxs-lookup"><span data-stu-id="965b8-110">Upload an app to a Line of Business, or upload a custom app to your Intune tenant.</span></span> <span data-ttu-id="965b8-111">Consulta también: Administración [de aplicaciones empresariales.](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management)</span><span class="sxs-lookup"><span data-stu-id="965b8-111">See also: [Enterprise app management](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management).</span></span>

2. <span data-ttu-id="965b8-112">[Asignar la aplicación a un grupo.](https://docs.microsoft.com/mem/intune/apps/apps-deploy)</span><span class="sxs-lookup"><span data-stu-id="965b8-112">[Assign your app to a group](https://docs.microsoft.com/mem/intune/apps/apps-deploy).</span></span> <span data-ttu-id="965b8-113">En función del tipo de asignación que elijas, la aplicación se puede entregar automáticamente o disponible para que se pueda retirar fácilmente si tienes una selección de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="965b8-113">Based on the assignment type you choose, the app can be delivered automatically or available to be readily pulled down if you have a selection of apps.</span></span>

> [!NOTE]
> <span data-ttu-id="965b8-114">Al compilar el paquete appx, asegúrate de incluir la arquitectura de los dispositivos en los que estás implementando.</span><span class="sxs-lookup"><span data-stu-id="965b8-114">When building your appx bundle make sure to account for including the architecture for the device(s) that you are deploying to.</span></span> <span data-ttu-id="965b8-115">HoloLens 2 es ARM64 y HoloLens (1.ª generación) es x86.</span><span class="sxs-lookup"><span data-stu-id="965b8-115">HoloLens 2 is ARM64, and HoloLens (1st Gen) is x86.</span></span> <span data-ttu-id="965b8-116">Puedes incluir ambos en un único paquete appx si tienes previsto tener un entorno de dispositivos mixtos.</span><span class="sxs-lookup"><span data-stu-id="965b8-116">You may include both in a single appx bundle if you plan on having a mixed devices environment.</span></span>

## <span data-ttu-id="965b8-117">Tipos de asignación</span><span class="sxs-lookup"><span data-stu-id="965b8-117">Assignment types</span></span>

<span data-ttu-id="965b8-118">Para que la aplicación se instale automáticamente en el dispositivo después de la inscripción, debes seleccionar **Necesario** para ese grupo o grupos.</span><span class="sxs-lookup"><span data-stu-id="965b8-118">To have your app to be automatically installed on the device after enrollment, you should select **Required** for that group(s).</span></span>
<span data-ttu-id="965b8-119">Para que la aplicación esté disponible para su descarga en dispositivos inscritos a través del portal de la empresa, selecciona **Disponible para dispositivos inscritos.**</span><span class="sxs-lookup"><span data-stu-id="965b8-119">To make your app available for download to devices enrolled through the company portal, select **Available for enrolled devices**.</span></span>

## <span data-ttu-id="965b8-120">End-User experiencia</span><span class="sxs-lookup"><span data-stu-id="965b8-120">End-User Experience</span></span>

<span data-ttu-id="965b8-121">Después de configurar la configuración en Intune, estará listo para que los usuarios finales reciban las aplicaciones seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="965b8-121">After you have set up configuration on Intune, you are ready for end users to receive your selected apps.</span></span>

<span data-ttu-id="965b8-122">Sigue estos pasos para obtener automáticamente las aplicaciones:</span><span class="sxs-lookup"><span data-stu-id="965b8-122">Follow these steps to automatically get your app(s):</span></span>

1. <span data-ttu-id="965b8-123">Inscriba el dispositivo en el espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="965b8-123">Enroll your device with your tenant.</span></span>
2. <span data-ttu-id="965b8-124">Una vez que el dispositivo haya completado la inscripción, debes recibir la aplicación en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="965b8-124">Once your device has completed enrollment, you should receive the app on your device.</span></span>
3. <span data-ttu-id="965b8-125">Si no ves la aplicación \*\*\*\* inmediatamente, ve a Cuentas de configuración Trabajo o Escuela información de tu cuenta y desplázate hacia abajo para ver información sobre  >  \*\*\*\*  >  \*\*\*\*  >  \*\* el estado de la aplicación instalada.</span><span class="sxs-lookup"><span data-stu-id="965b8-125">If you are not seeing you app immediately, go to **Settings** > **Accounts** > **Work or School** > *your account* Info, and scroll down to see information on installed app status.</span></span>

<span data-ttu-id="965b8-126">Cómo obtener acceso a las aplicaciones a través del Portal de empresa:</span><span class="sxs-lookup"><span data-stu-id="965b8-126">How to get to apps through the Company Portal:</span></span>

1. <span data-ttu-id="965b8-127">Abre el **menú Inicio** y selecciona **Microsoft Store.**</span><span class="sxs-lookup"><span data-stu-id="965b8-127">Open the **Start Menu** and select **Microsoft Store**.</span></span>
2. <span data-ttu-id="965b8-128">Busque el **Portal de empresa** y descargue la aplicación.</span><span class="sxs-lookup"><span data-stu-id="965b8-128">Search for **Company Portal** and download the app.</span></span>
3. <span data-ttu-id="965b8-129">Inicia sesión en tu cuenta.</span><span class="sxs-lookup"><span data-stu-id="965b8-129">Sign into your account.</span></span>
4. <span data-ttu-id="965b8-130">Selecciona la aplicación que quieras recibir y descargarla.</span><span class="sxs-lookup"><span data-stu-id="965b8-130">Select the app you wish to receive and download it.</span></span>

> [!Tip]
> <span data-ttu-id="965b8-131">Obtenga más información [sobre la instalación automática del Portal](https://docs.microsoft.com/mem/intune/apps/company-portal-app) de empresa y la implementación y administración de aplicaciones en [Intune.](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)</span><span class="sxs-lookup"><span data-stu-id="965b8-131">Learn more about [auto-installing the Company Portal](https://docs.microsoft.com/mem/intune/apps/company-portal-app) and [deploying and managing apps in Intune](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).</span></span>
