---
title: Paquete de aprovisionamiento
description: aplicación, implementación de aplicaciones, aplicación empresarial demployment, aprovisionamiento
keywords: aplicación, implementación de aplicaciones, aplicación empresarial demployment, aprovisionamiento
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 0803b5f1b77ac7f123d534d101cd24903b87094c
ms.sourcegitcommit: 89ce6cdc0fc6d70a88217791c5f6d613778af614
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "11052587"
---
# <span data-ttu-id="e0426-104">Paquete de aprovisionamiento</span><span class="sxs-lookup"><span data-stu-id="e0426-104">Provisioning Package</span></span>

<span data-ttu-id="e0426-105">Los paquetes de aprovisionamiento se pueden usar para preparar y configurar dispositivos en un entorno sin acceso a administración de extremos.</span><span class="sxs-lookup"><span data-stu-id="e0426-105">Provisioning packages can be used to prepare and configure devices in an environment without access to endpoint management.</span></span> <span data-ttu-id="e0426-106">También se pueden implementar en un dispositivo, independientemente de la identidad del usuario, el estado de inscripción, durante la configuración rápida (OOBE) o [aplicando un paquete de aprovisionamiento durante la configuración](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).</span><span class="sxs-lookup"><span data-stu-id="e0426-106">They can also be deployed to a device regardless of identity of the user, enrollment status, during the Out of Box Experience (OOBE), or by [applying a provisioning package during setup](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).</span></span>

## <span data-ttu-id="e0426-107">Consideraciones sobre los paquetes de aprovisionamiento:</span><span class="sxs-lookup"><span data-stu-id="e0426-107">Provisioning Packages considerations:</span></span>
* <span data-ttu-id="e0426-108">Aplicaciones no públicas</span><span class="sxs-lookup"><span data-stu-id="e0426-108">Non-Public apps</span></span>
* <span data-ttu-id="e0426-109">Solo carga del lado USB</span><span class="sxs-lookup"><span data-stu-id="e0426-109">USB side-load only</span></span>
* <span data-ttu-id="e0426-110">No hay ninguna actualización automática (requiere actualizaciones manuales a través de PPKGs)</span><span class="sxs-lookup"><span data-stu-id="e0426-110">No auto update (requires manual updates via PPKGs)</span></span>

> [!NOTE] 
> <span data-ttu-id="e0426-111">Para obtener información sobre los conceptos básicos de la creación de un paquete de aprovisionamiento para dispositivos HoloLens, visite la [configuración de hololens](https://docs.microsoft.com/hololens/hololens-provisioning).</span><span class="sxs-lookup"><span data-stu-id="e0426-111">To learn the basics of creating a Provisioning Package for HoloLens devices, visit [HoloLens Provisioning](https://docs.microsoft.com/hololens/hololens-provisioning).</span></span> <span data-ttu-id="e0426-112">Para implementar una aplicación, debe empezar con el aprovisionamiento avanzado.</span><span class="sxs-lookup"><span data-stu-id="e0426-112">To deploy an app, you must start with advanced provisioning.</span></span> 

> [!NOTE] 
> <span data-ttu-id="e0426-113">HoloLens (1º gen) tiene un soporte limitado para instalar aplicaciones (**UniversalAppInstall**) mediante un paquete de aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="e0426-113">HoloLens (1st gen) has limited support installing apps (**UniversalAppInstall**) by using a provisioning package.</span></span> <span data-ttu-id="e0426-114">Los dispositivos HoloLens (1. ª gen) solo admiten la instalación de una aplicación a través de PPKG solo durante OOBE y solo con instalaciones de contexto de usuario.</span><span class="sxs-lookup"><span data-stu-id="e0426-114">HoloLens (1st gen) devices only support installing an app via PPKG only during OOBE and only with user context installs.</span></span>

## <span data-ttu-id="e0426-115">Programa de instalación</span><span class="sxs-lookup"><span data-stu-id="e0426-115">Setup</span></span>

<span data-ttu-id="e0426-116">En el [Diseñador de configuración de Windows](https://www.microsoft.com/store/productId/9NBLGGH4TX22) , siga 4 pasos.</span><span class="sxs-lookup"><span data-stu-id="e0426-116">Within [Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) take following 4 steps.</span></span>

1. <span data-ttu-id="e0426-117">Establece ApplicationManagement/AllowAllTrustedApps en "sí".</span><span class="sxs-lookup"><span data-stu-id="e0426-117">Set ApplicationManagement/AllowAllTrustedApps To “Yes”.</span></span> <span data-ttu-id="e0426-118">Consulte: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span><span class="sxs-lookup"><span data-stu-id="e0426-118">See: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span></span>
2. <span data-ttu-id="e0426-119">En **UniversalAppInstall**  >  **UserContextAppLicense** introduce el **PackageFamilyName**.</span><span class="sxs-lookup"><span data-stu-id="e0426-119">Under **UniversalAppInstall** > **UserContextAppLicense** please enter the **PackageFamilyName**.</span></span> <span data-ttu-id="e0426-120">Consulta [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall).</span><span class="sxs-lookup"><span data-stu-id="e0426-120">See [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall).</span></span> <span data-ttu-id="e0426-121">Vea también: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span><span class="sxs-lookup"><span data-stu-id="e0426-121">See also: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span></span>
    - <span data-ttu-id="e0426-122">Si no lo conoces, puedes usar Device portal en un dispositivo en el que ya hayas instalado la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e0426-122">If you don’t know this, you can use Device Portal on a device you have already installed your app to.</span></span> <span data-ttu-id="e0426-123">Visite la página aplicaciones y mire la línea PackageRelativeID, toda la información antes de la "!" Es tu **PackageFamilyName**.</span><span class="sxs-lookup"><span data-stu-id="e0426-123">Visit the Apps page, and look at the PackageRelativeID line, all the information before the "!" Is your **PackageFamilyName**.</span></span>
3. <span data-ttu-id="e0426-124">Verá que tiene una nueva sección, **ApplicationFile**.</span><span class="sxs-lookup"><span data-stu-id="e0426-124">You will then see that you have a new section, **ApplicationFile**.</span></span> <span data-ttu-id="e0426-125">Usa este área para cargar tu paquete appx.</span><span class="sxs-lookup"><span data-stu-id="e0426-125">Use this area to upload your appx bundle.</span></span> 
4. <span data-ttu-id="e0426-126">En función de si ha comprado la aplicación o ha creado su propia aplicación de LOB, tendrá que cargar el archivo de licencia o el certificado de seguridad.</span><span class="sxs-lookup"><span data-stu-id="e0426-126">Depending on if you have purchased your app or built your own LOB app, you will need to upload the license file or security certificate.</span></span>
    - <span data-ttu-id="e0426-127">Para el archivo de licencia: en **UniversalAppInstall**  >  **UserContextAppLience** y vaya a la ubicación de su licencia y cargarla.</span><span class="sxs-lookup"><span data-stu-id="e0426-127">For license file: Under **UniversalAppInstall** > **UserContextAppLience** and browse to the location of your license and upload it.</span></span> 
    - <span data-ttu-id="e0426-128">Para el archivo de seguridad, navegue hasta **certificados** y seleccione el certificado para instalar junto a su paquete. appx.</span><span class="sxs-lookup"><span data-stu-id="e0426-128">For security file navigate to **Certificates** and select your certificate to install alongside your .appx bundle.</span></span> 

<span data-ttu-id="e0426-129">Asegúrese de guardar el proyecto en una ubicación segura.</span><span class="sxs-lookup"><span data-stu-id="e0426-129">Make sure to save your project to a secure location.</span></span> <span data-ttu-id="e0426-130">A continuación, **expórtelo** como un **paquete de aprovisionamiento**.</span><span class="sxs-lookup"><span data-stu-id="e0426-130">Then **Export** it as a **Provisioning Package**.</span></span>  
    
<span data-ttu-id="e0426-131">Consulta también: [aplicar tu paquete de provisiong a HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span><span class="sxs-lookup"><span data-stu-id="e0426-131">See also: [Apply your provisiong package to HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span></span>
