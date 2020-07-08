---
title: Paquete de aprovisionamiento
description: aplicación, implementación de aplicaciones, aplicación empresarial demployment, aprovisionamiento
keywords: aplicación, implementación de aplicaciones, aplicación empresarial demployment, aprovisionamiento
author: v-jodben
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
ms.openlocfilehash: 7417f9e8cf1921d9fdb57dbd96fff094e21c44f9
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857949"
---
# <span data-ttu-id="da103-104">Paquete de aprovisionamiento</span><span class="sxs-lookup"><span data-stu-id="da103-104">Provisioning Package</span></span>

<span data-ttu-id="da103-105">Los paquetes de aprovisionamiento se pueden usar para preparar y configurar dispositivos en un entorno sin acceso a administración de extremos.</span><span class="sxs-lookup"><span data-stu-id="da103-105">Provisioning packages can be used to prepare and configure devices in an environment without access to endpoint management.</span></span> <span data-ttu-id="da103-106">También se pueden implementar en un dispositivo, independientemente de la identidad del usuario, el estado de inscripción, durante la configuración rápida (OOBE) o [aplicando un paquete de aprovisionamiento durante la configuración](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).</span><span class="sxs-lookup"><span data-stu-id="da103-106">They can also be deployed to a device regardless of identity of the user, enrollment status, during the Out of Box Experience (OOBE), or by [applying a provisioning package during setup](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).</span></span>

## <span data-ttu-id="da103-107">Consideraciones sobre los paquetes de aprovisionamiento:</span><span class="sxs-lookup"><span data-stu-id="da103-107">Provisioning Packages considerations:</span></span>
* <span data-ttu-id="da103-108">Aplicaciones no públicas</span><span class="sxs-lookup"><span data-stu-id="da103-108">Non-Public apps</span></span>
* <span data-ttu-id="da103-109">Solo carga del lado USB</span><span class="sxs-lookup"><span data-stu-id="da103-109">USB side-load only</span></span>
* <span data-ttu-id="da103-110">No hay ninguna actualización automática (requiere actualizaciones manuales a través de PPKGs)</span><span class="sxs-lookup"><span data-stu-id="da103-110">No auto update (requires manual updates via PPKGs)</span></span>

> [!NOTE] 
> <span data-ttu-id="da103-111">Para obtener información sobre los conceptos básicos de la creación de un paquete de aprovisionamiento para dispositivos HoloLens, visite la [configuración de hololens](https://docs.microsoft.com/hololens/hololens-provisioning).</span><span class="sxs-lookup"><span data-stu-id="da103-111">To learn the basics of creating a Provisioning Package for HoloLens devices, visit [HoloLens Provisioning](https://docs.microsoft.com/hololens/hololens-provisioning).</span></span> <span data-ttu-id="da103-112">Para implementar una aplicación, debe empezar con el aprovisionamiento avanzado.</span><span class="sxs-lookup"><span data-stu-id="da103-112">To deploy an app, you must start with advanced provisioning.</span></span> 

## <span data-ttu-id="da103-113">Programa de instalación</span><span class="sxs-lookup"><span data-stu-id="da103-113">Setup</span></span>

<span data-ttu-id="da103-114">En el [Diseñador de configuración de Windows](https://www.microsoft.com/store/productId/9NBLGGH4TX22) , siga 4 pasos.</span><span class="sxs-lookup"><span data-stu-id="da103-114">Within [Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) take following 4 steps.</span></span>

1. <span data-ttu-id="da103-115">Establece ApplicationManagement/AllowAllTrustedApps en "sí".</span><span class="sxs-lookup"><span data-stu-id="da103-115">Set ApplicationManagement/AllowAllTrustedApps To “Yes”.</span></span> <span data-ttu-id="da103-116">Consulte: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span><span class="sxs-lookup"><span data-stu-id="da103-116">See: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span></span>
2. <span data-ttu-id="da103-117">En **UniversalAppInstall**  >  **UserContextAppLicense** introduce el **PackageFamilyName**.</span><span class="sxs-lookup"><span data-stu-id="da103-117">Under **UniversalAppInstall** > **UserContextAppLicense** please enter the **PackageFamilyName**.</span></span> <span data-ttu-id="da103-118">Consulta [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall).</span><span class="sxs-lookup"><span data-stu-id="da103-118">See [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall).</span></span> <span data-ttu-id="da103-119">Vea también: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span><span class="sxs-lookup"><span data-stu-id="da103-119">See also: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span></span>
    - <span data-ttu-id="da103-120">Si no lo conoces, puedes usar Device portal en un dispositivo en el que ya hayas instalado la aplicación.</span><span class="sxs-lookup"><span data-stu-id="da103-120">If you don’t know this, you can use Device Portal on a device you have already installed your app to.</span></span> <span data-ttu-id="da103-121">Visite la página aplicaciones y mire la línea PackageRelativeID, toda la información antes de la "!" Es tu **PackageFamilyName**.</span><span class="sxs-lookup"><span data-stu-id="da103-121">Visit the Apps page, and look at the PackageRelativeID line, all the information before the "!" Is your **PackageFamilyName**.</span></span>
3. <span data-ttu-id="da103-122">Verá que tiene una nueva sección, **ApplicationFile**.</span><span class="sxs-lookup"><span data-stu-id="da103-122">You will then see that you have a new section, **ApplicationFile**.</span></span> <span data-ttu-id="da103-123">Usa este área para cargar tu paquete appx.</span><span class="sxs-lookup"><span data-stu-id="da103-123">Use this area to upload your appx bundle.</span></span> 
4. <span data-ttu-id="da103-124">En función de si ha comprado la aplicación o ha creado su propia aplicación de LOB, tendrá que cargar el archivo de licencia o el certificado de seguridad.</span><span class="sxs-lookup"><span data-stu-id="da103-124">Depending on if you have purchased your app or built your own LOB app, you will need to upload the license file or security certificate.</span></span>
    - <span data-ttu-id="da103-125">Para el archivo de licencia: en **UniversalAppInstall**  >  **UserContextAppLience** y vaya a la ubicación de su licencia y cargarla.</span><span class="sxs-lookup"><span data-stu-id="da103-125">For license file: Under **UniversalAppInstall** > **UserContextAppLience** and browse to the location of your license and upload it.</span></span> 
    - <span data-ttu-id="da103-126">Para el archivo de seguridad, navegue hasta **certificados** y seleccione el certificado para instalar junto a su paquete. appx.</span><span class="sxs-lookup"><span data-stu-id="da103-126">For security file navigate to **Certificates** and select your certificate to install alongside your .appx bundle.</span></span> 

<span data-ttu-id="da103-127">Asegúrese de guardar el proyecto en una ubicación segura.</span><span class="sxs-lookup"><span data-stu-id="da103-127">Make sure to save your project to a secure location.</span></span> <span data-ttu-id="da103-128">A continuación, **expórtelo** como un **paquete de aprovisionamiento**.</span><span class="sxs-lookup"><span data-stu-id="da103-128">Then **Export** it as a **Provisioning Package**.</span></span>  
    
<span data-ttu-id="da103-129">Consulta también: [aplicar tu paquete de provisiong a HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span><span class="sxs-lookup"><span data-stu-id="da103-129">See also: [Apply your provisiong package to HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span></span>
