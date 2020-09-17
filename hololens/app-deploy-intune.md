---
title: Intune y portal de la empresa
description: Intune, administración de aplicaciones, aplicación, portal de la empresa, portal
keywords: Intune, administración de aplicaciones, aplicación, portal de la empresa, portal, hololens
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
ms.openlocfilehash: 55e2b15808e52bb80e8114e215bc0cef52358842
ms.sourcegitcommit: 785ac6f05aecffc0f3980960891617d161711a70
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2020
ms.locfileid: "11016674"
---
# <span data-ttu-id="3539e-104">Portal de empresa e Intune</span><span class="sxs-lookup"><span data-stu-id="3539e-104">Intune & Company Portal</span></span>

<span data-ttu-id="3539e-105">Con la administración de dispositivos móviles (MDM), puedes usar tus propias aplicaciones personalizadas a través de [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) para implementarlo directamente en tus dispositivos HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3539e-105">With Mobile Device Management (MDM), you can use your own custom apps through [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) to deploy it directly to your HoloLens devices.</span></span> <span data-ttu-id="3539e-106">Microsoft Intune es un servicio basado en la nube que se centra en la administración de dispositivos móviles (MDM) y la administración de aplicaciones móviles (MAM).</span><span class="sxs-lookup"><span data-stu-id="3539e-106">Microsoft Intune is a cloud-based service that focuses on mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="3539e-107">Intune está incluido en el[conjunto de programas de seguridad y movilidad empresarial](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)de Microsoft y permite que los usuarios sean productivos mientras mantienen protegidos los datos de su organización.</span><span class="sxs-lookup"><span data-stu-id="3539e-107">Intune is included in Microsoft's[Enterprise Mobility + Security (EMS) suite](https://www.microsoft.com/microsoft-365/enterprise-mobility-security), and enables users to be productive while keeping your organization data protected.</span></span> <span data-ttu-id="3539e-108">Para obtener más información sobre Intune, lea [lo que es Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune).</span><span class="sxs-lookup"><span data-stu-id="3539e-108">To learn more about Intune, please read [What is Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune).</span></span>

## <span data-ttu-id="3539e-109">Programa de instalación</span><span class="sxs-lookup"><span data-stu-id="3539e-109">Setup</span></span>

1. <span data-ttu-id="3539e-110">Cargue una aplicación a una línea de negocio o cargue una aplicación personalizada a su inquilino de Intune.</span><span class="sxs-lookup"><span data-stu-id="3539e-110">Upload an app to a Line of Business, or upload a custom app to your Intune tenant.</span></span> <span data-ttu-id="3539e-111">Vea también: [Administración de aplicaciones empresariales](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management).</span><span class="sxs-lookup"><span data-stu-id="3539e-111">See also: [Enterprise app management](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management).</span></span>

2. <span data-ttu-id="3539e-112">[Asignar la aplicación a un grupo](https://docs.microsoft.com/mem/intune/apps/apps-deploy).</span><span class="sxs-lookup"><span data-stu-id="3539e-112">[Assign your app to a group](https://docs.microsoft.com/mem/intune/apps/apps-deploy).</span></span> <span data-ttu-id="3539e-113">Según el tipo de asignación que elija, puede hacer que la aplicación se entregue de forma automática o disponible para que se extraiga fácilmente si tiene una selección de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="3539e-113">Based on the assignment type you choose you can have the app delivered automatically or available to be readily pulled down if you have a selection of apps.</span></span> 

> [!NOTE] 
> <span data-ttu-id="3539e-114">Al crear tu paquete appx, asegúrate de incluir la arquitectura de los dispositivos en los que estás implementando.</span><span class="sxs-lookup"><span data-stu-id="3539e-114">When building your appx bundle make sure to account for including the architecture for the device(s) that you are deploying to.</span></span> <span data-ttu-id="3539e-115">HoloLens 2 es ARM64, y HoloLens (1º gen) es x86.</span><span class="sxs-lookup"><span data-stu-id="3539e-115">HoloLens 2 is ARM64, and HoloLens (1st Gen) is x86.</span></span> <span data-ttu-id="3539e-116">Si tienes pensados en un entorno de dispositivos mixtos, puedes incluir ambos en un solo paquete appx.</span><span class="sxs-lookup"><span data-stu-id="3539e-116">You may include both in a single appx bundle if you plan on having a mixed devices environment.</span></span>

## <span data-ttu-id="3539e-117">Tipos de asignación</span><span class="sxs-lookup"><span data-stu-id="3539e-117">Assignment types</span></span>

<span data-ttu-id="3539e-118">Si prefiere que su aplicación se instale automáticamente en el dispositivo después de la inscripción, debe seleccionar **obligatorio** para ese grupo (s).</span><span class="sxs-lookup"><span data-stu-id="3539e-118">If you prefer your app to be automatically installed on the device after enrollment, you should select **Required** for that group(s).</span></span>
<span data-ttu-id="3539e-119">Si prefiere que la aplicación esté disponible para su descarga a las que se han inscrito a través del portal de la empresa, seleccione **disponible para dispositivos inscritos**.</span><span class="sxs-lookup"><span data-stu-id="3539e-119">If you prefer to make your app available for download to those enrolled through the company portal, select **Available for enrolled devices**.</span></span>


## <span data-ttu-id="3539e-120">Experiencia de usuario final</span><span class="sxs-lookup"><span data-stu-id="3539e-120">End User Experience</span></span>

<span data-ttu-id="3539e-121">Una vez que haya configurado la configuración de Intune, estará listo para que los usuarios finales reciban las aplicaciones seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="3539e-121">After you have set up configuration on Intune you are ready for end users to recieve your selected apps.</span></span>

<span data-ttu-id="3539e-122">Siga estos pasos para obtener automáticamente las aplicaciones:</span><span class="sxs-lookup"><span data-stu-id="3539e-122">Follow these steps to automatically get your app(s):</span></span>
1. <span data-ttu-id="3539e-123">Inscriba el dispositivo en el inquilino.</span><span class="sxs-lookup"><span data-stu-id="3539e-123">Enroll your device with your tenant.</span></span> 
2. <span data-ttu-id="3539e-124">Una vez que el dispositivo haya finalizado la inscripción, deberás recibir la aplicación en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3539e-124">Once your device has completed enrollment, you should receive the app on your device.</span></span> 
3. <span data-ttu-id="3539e-125">Si no ve la aplicación inmediatamente, vaya a **configuración**  >  **cuentas**  >  **de trabajo o en la escuela**  >  **youraccount** información y desplácese hacia abajo para ver información sobre el estado de la aplicación instalada.</span><span class="sxs-lookup"><span data-stu-id="3539e-125">If you are not seeing you app immediately, go to **Settings** > **Accounts** > **Work or School** > **youraccount** Info, and scroll down to see information on installed app status.</span></span>

<span data-ttu-id="3539e-126">Cómo acceder a las aplicaciones a través del portal de la empresa:</span><span class="sxs-lookup"><span data-stu-id="3539e-126">How to get to apps through the Company Portal:</span></span>
1. <span data-ttu-id="3539e-127">Abra el **menú Inicio** y seleccione **Microsoft Store**.</span><span class="sxs-lookup"><span data-stu-id="3539e-127">Open the **Start Menu** and select **Microsoft Store**.</span></span> 
2. <span data-ttu-id="3539e-128">Busca el **portal** de la empresa y descarga la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3539e-128">Search for **Company Portal** and download the app.</span></span>
3. <span data-ttu-id="3539e-129">Inicia sesión en tu cuenta.</span><span class="sxs-lookup"><span data-stu-id="3539e-129">Sign into your account.</span></span>
4. <span data-ttu-id="3539e-130">Seleccione la aplicación que desea recibir y descargarla.</span><span class="sxs-lookup"><span data-stu-id="3539e-130">Select the app you wish to receive and download it.</span></span>

> [!Tip]
> <span data-ttu-id="3539e-131">Obtenga más información acerca de [la instalación automática del portal de la empresa](https://docs.microsoft.com/mem/intune/apps/company-portal-app) y [de la implementación y administración de aplicaciones en Intune](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).</span><span class="sxs-lookup"><span data-stu-id="3539e-131">Learn more about [auto-installing the Company Portal](https://docs.microsoft.com/mem/intune/apps/company-portal-app) and [deploying and managing apps in Intune](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).</span></span>
