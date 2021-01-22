---
title: Paquete de aprovisionamiento
description: Obtén información sobre el empaquetado, el aprovisionamiento, la implementación y la implementación de aplicaciones empresariales para dispositivos HoloLens.
keywords: aplicación, implementación de aplicaciones, implementación de aplicaciones empresariales, aprovisionamiento
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
ms.openlocfilehash: 9c73b03e6a8dca6baf6c58fed091df96994c3780
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283701"
---
# <span data-ttu-id="17946-104">Paquete de aprovisionamiento</span><span class="sxs-lookup"><span data-stu-id="17946-104">Provisioning Package</span></span>

<span data-ttu-id="17946-105">Los paquetes de aprovisionamiento se pueden usar para preparar y configurar dispositivos en un entorno sin acceso a la administración de puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="17946-105">Provisioning packages can be used to prepare and configure devices in an environment without access to endpoint management.</span></span> <span data-ttu-id="17946-106">También se pueden implementar en un dispositivo independientemente de la identidad del usuario, el estado de inscripción, durante la configuración rápida (OOBE) o aplicando un paquete de aprovisionamiento durante la [instalación.](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)</span><span class="sxs-lookup"><span data-stu-id="17946-106">They can also be deployed to a device regardless of identity of the user, enrollment status, during the Out of Box Experience (OOBE), or by [applying a provisioning package during setup](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).</span></span>

## <span data-ttu-id="17946-107">Consideraciones sobre paquetes de aprovisionamiento:</span><span class="sxs-lookup"><span data-stu-id="17946-107">Provisioning Packages considerations:</span></span>

* <span data-ttu-id="17946-108">Aplicaciones no públicas</span><span class="sxs-lookup"><span data-stu-id="17946-108">Non-Public apps</span></span>
* <span data-ttu-id="17946-109">Solo carga lateral USB</span><span class="sxs-lookup"><span data-stu-id="17946-109">USB side-load only</span></span>
* <span data-ttu-id="17946-110">No hay actualización automática (requiere actualizaciones manuales a través de PPKG)</span><span class="sxs-lookup"><span data-stu-id="17946-110">No auto update (requires manual updates via PPKGs)</span></span>

<span data-ttu-id="17946-111">Las aplicaciones instaladas a través de un paquete de aprovisionamiento deben estar firmadas por un certificado en el almacén del equipo local.</span><span class="sxs-lookup"><span data-stu-id="17946-111">Apps installed via a provisioning package must be signed by a certificate in the local machine store.</span></span> <span data-ttu-id="17946-112">Los paquetes de aprovisionamiento solo pueden instalar certificados en el almacén del dispositivo (equipo local), por lo que es posible que se instalen una aplicación y un certificado a través del mismo paquete de aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="17946-112">Provisioning packages can only install certificates to the device (local machine) store, therefore an app and certificate may be installed via the same provisioning package.</span></span> <span data-ttu-id="17946-113">Si vas a implementar el certificado desde MDM o instalarlo a través del Administrador de [certificados,](certificate-manager.md)asegúrate de implementar el certificado en el almacén del equipo local para firmar las aplicaciones instaladas de esta forma.</span><span class="sxs-lookup"><span data-stu-id="17946-113">If you are deploying your certificate from MDM or installing via the [Certificate Manager](certificate-manager.md), make sure to deploy the certificate to the local machine store to sign apps installed this way.</span></span>

<span data-ttu-id="17946-114">Para obtener información sobre los conceptos básicos de la creación de un paquete de aprovisionamiento para dispositivos HoloLens, visita [Aprovisionamiento de HoloLens.](https://docs.microsoft.com/hololens/hololens-provisioning)</span><span class="sxs-lookup"><span data-stu-id="17946-114">To learn the basics of creating a Provisioning Package for HoloLens devices, visit [HoloLens Provisioning](https://docs.microsoft.com/hololens/hololens-provisioning).</span></span> <span data-ttu-id="17946-115">Para implementar una aplicación, debes empezar con el aprovisionamiento avanzado.</span><span class="sxs-lookup"><span data-stu-id="17946-115">To deploy an app, you must start with advanced provisioning.</span></span>

> [!NOTE]
> <span data-ttu-id="17946-116">HoloLens (1.ª generación) tiene compatibilidad limitada para instalar aplicaciones (**UniversalAppInstall**) mediante un paquete de aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="17946-116">HoloLens (1st gen) has limited support installing apps (**UniversalAppInstall**) by using a provisioning package.</span></span> <span data-ttu-id="17946-117">Los dispositivos HoloLens (1.ª generación) solo admiten la instalación de una aplicación a través de PPKG solo durante la OOBE y solo con las instalaciones de contexto de usuario.</span><span class="sxs-lookup"><span data-stu-id="17946-117">HoloLens (1st gen) devices only support installing an app via PPKG only during OOBE and only with user context installs.</span></span>

## <span data-ttu-id="17946-118">Programa de instalación</span><span class="sxs-lookup"><span data-stu-id="17946-118">Setup</span></span>

<span data-ttu-id="17946-119">En [el Diseñador de configuraciones de Windows,](https://www.microsoft.com/store/productId/9NBLGGH4TX22) siga estos cuatro pasos.</span><span class="sxs-lookup"><span data-stu-id="17946-119">Within [Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) take following four steps.</span></span>

1. <span data-ttu-id="17946-120">Establezca ApplicationManagement/AllowAllTrustedApps en "Sí".</span><span class="sxs-lookup"><span data-stu-id="17946-120">Set ApplicationManagement/AllowAllTrustedApps To “Yes”.</span></span> <span data-ttu-id="17946-121">Vea: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span><span class="sxs-lookup"><span data-stu-id="17946-121">See: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span></span>

2. <span data-ttu-id="17946-122">Vaya a **UniversalAppInstall**  >  **UserContextAppLicense** y escriba **PackageFamilyName**.</span><span class="sxs-lookup"><span data-stu-id="17946-122">Navigate to **UniversalAppInstall** > **UserContextAppLicense** enter the **PackageFamilyName**.</span></span> <span data-ttu-id="17946-123">Vea [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall).</span><span class="sxs-lookup"><span data-stu-id="17946-123">See [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall).</span></span> <span data-ttu-id="17946-124">Vea también: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span><span class="sxs-lookup"><span data-stu-id="17946-124">See also: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span></span>

   <span data-ttu-id="17946-125">Puedes usar Device Portal en un dispositivo en el que ya has instalado la aplicación.</span><span class="sxs-lookup"><span data-stu-id="17946-125">You can use Device Portal on a device you have already installed your app to.</span></span> <span data-ttu-id="17946-126">Visita la página Aplicaciones y mira la línea PackageRelativeID, toda la información antes de "!". Es **packageFamilyName**.</span><span class="sxs-lookup"><span data-stu-id="17946-126">Visit the Apps page, and look at the PackageRelativeID line, all the information before the "!" Is your **PackageFamilyName**.</span></span>

3. <span data-ttu-id="17946-127">A continuación, verá que tiene una nueva sección, **ApplicationFile**.</span><span class="sxs-lookup"><span data-stu-id="17946-127">You will then see that you have a new section, **ApplicationFile**.</span></span> <span data-ttu-id="17946-128">Usa esta área para cargar el lote appx.</span><span class="sxs-lookup"><span data-stu-id="17946-128">Use this area to upload your appx bundle.</span></span>

4. <span data-ttu-id="17946-129">Dependiendo de si has comprado la aplicación o creado tu propia aplicación de LÍNEA de negocio, deberás cargar el archivo de licencia o el certificado de seguridad.</span><span class="sxs-lookup"><span data-stu-id="17946-129">Depending on if you have purchased your app or built your own LOB app, you will need to upload the license file or security certificate.</span></span>

    - <span data-ttu-id="17946-130">Para el archivo de licencia: vaya a **UniversalAppInstall**  >  **UserContextAppLicence** y vaya a la ubicación de la licencia y cárbala.</span><span class="sxs-lookup"><span data-stu-id="17946-130">For license file: navigate to **UniversalAppInstall** > **UserContextAppLicence** and browse to the location of your license and upload it.</span></span>
    - <span data-ttu-id="17946-131">Para el archivo de seguridad, ve **a Certificados** y selecciona el certificado que quieres instalar junto con la agrupación .appx.</span><span class="sxs-lookup"><span data-stu-id="17946-131">For the security file, navigate to **Certificates** and select your certificate to install alongside your .appx bundle.</span></span>

<span data-ttu-id="17946-132">Asegúrese de guardar el proyecto en una ubicación segura.</span><span class="sxs-lookup"><span data-stu-id="17946-132">Make sure to save your project to a secure location.</span></span> <span data-ttu-id="17946-133">A **continuación,** exportarlo como un paquete **de aprovisionamiento**.</span><span class="sxs-lookup"><span data-stu-id="17946-133">Then **Export** it as a **Provisioning Package**.</span></span>  

<span data-ttu-id="17946-134">Vea también: [Aplicar el paquete de aprovisionamiento a HoloLens.](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup)</span><span class="sxs-lookup"><span data-stu-id="17946-134">See also: [Apply your provisioning package to HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span></span>
