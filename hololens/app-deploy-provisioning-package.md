---
title: Paquete de aprovisionamiento
description: Obtenga información sobre el empaquetado de aplicaciones, el aprovisionamiento, la implementación y la implementación de aplicaciones empresariales para HoloLens dispositivos.
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
ms.openlocfilehash: 5aa554f9e7fdc09c3112b628e0978ac3332bc57d
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635524"
---
# <a name="provisioning-package"></a><span data-ttu-id="39efe-104">Paquete de aprovisionamiento</span><span class="sxs-lookup"><span data-stu-id="39efe-104">Provisioning Package</span></span>

<span data-ttu-id="39efe-105">Los paquetes de aprovisionamiento se pueden usar para preparar y configurar dispositivos en un entorno sin acceso a la administración de puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="39efe-105">Provisioning packages can be used to prepare and configure devices in an environment without access to endpoint management.</span></span> <span data-ttu-id="39efe-106">También se pueden implementar en un dispositivo independientemente de la identidad del usuario, el estado de inscripción, durante la experiencia rápida (OOBE) o mediante la aplicación de un paquete de [aprovisionamiento](/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)durante la instalación .</span><span class="sxs-lookup"><span data-stu-id="39efe-106">They can also be deployed to a device regardless of identity of the user, enrollment status, during the Out of Box Experience (OOBE), or by [applying a provisioning package during setup](/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).</span></span>

## <a name="provisioning-packages-considerations"></a><span data-ttu-id="39efe-107">Consideraciones sobre los paquetes de aprovisionamiento:</span><span class="sxs-lookup"><span data-stu-id="39efe-107">Provisioning Packages considerations:</span></span>

* <span data-ttu-id="39efe-108">Aplicaciones no públicas</span><span class="sxs-lookup"><span data-stu-id="39efe-108">Non-Public apps</span></span>
* <span data-ttu-id="39efe-109">Solo carga lateral USB</span><span class="sxs-lookup"><span data-stu-id="39efe-109">USB side-load only</span></span>
* <span data-ttu-id="39efe-110">Sin actualización automática (requiere actualizaciones manuales a través de PPKG)</span><span class="sxs-lookup"><span data-stu-id="39efe-110">No auto update (requires manual updates via PPKGs)</span></span>

<span data-ttu-id="39efe-111">Las aplicaciones instaladas a través de un paquete de aprovisionamiento deben estar firmadas por un certificado en el almacén de la máquina local.</span><span class="sxs-lookup"><span data-stu-id="39efe-111">Apps installed via a provisioning package must be signed by a certificate in the local machine store.</span></span> <span data-ttu-id="39efe-112">Los paquetes de aprovisionamiento solo pueden instalar certificados en el almacén del dispositivo (equipo local), por lo que se puede instalar una aplicación y un certificado a través del mismo paquete de aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="39efe-112">Provisioning packages can only install certificates to the device (local machine) store, therefore an app and certificate may be installed via the same provisioning package.</span></span> <span data-ttu-id="39efe-113">Si va a implementar el certificado desde MDM o instalarlo a través del Administrador de [certificados,](certificate-manager.md)asegúrese de implementar el certificado en el almacén de la máquina local para firmar las aplicaciones instaladas de esta manera.</span><span class="sxs-lookup"><span data-stu-id="39efe-113">If you are deploying your certificate from MDM or installing via the [Certificate Manager](certificate-manager.md), make sure to deploy the certificate to the local machine store to sign apps installed this way.</span></span>

<span data-ttu-id="39efe-114">Para conocer los conceptos básicos de la creación de un paquete de aprovisionamiento para HoloLens dispositivos, [visite HoloLens Provisioning](/hololens/hololens-provisioning).</span><span class="sxs-lookup"><span data-stu-id="39efe-114">To learn the basics of creating a Provisioning Package for HoloLens devices, visit [HoloLens Provisioning](/hololens/hololens-provisioning).</span></span> <span data-ttu-id="39efe-115">Para implementar una aplicación, debe empezar con el aprovisionamiento avanzado.</span><span class="sxs-lookup"><span data-stu-id="39efe-115">To deploy an app, you must start with advanced provisioning.</span></span>

> [!NOTE]
> <span data-ttu-id="39efe-116">HoloLens (1.ª generación) tiene compatibilidad limitada con la instalación de aplicaciones **(UniversalAppInstall)** mediante un paquete de aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="39efe-116">HoloLens (1st gen) has limited support installing apps (**UniversalAppInstall**) by using a provisioning package.</span></span> <span data-ttu-id="39efe-117">HoloLens (1.ª generación) solo admiten la instalación de una aplicación a través de PPKG solo durante OOBE y solo con las instalaciones de contexto de usuario.</span><span class="sxs-lookup"><span data-stu-id="39efe-117">HoloLens (1st gen) devices only support installing an app via PPKG only during OOBE and only with user context installs.</span></span>

## <a name="setup"></a><span data-ttu-id="39efe-118">Configurar</span><span class="sxs-lookup"><span data-stu-id="39efe-118">Setup</span></span>

<span data-ttu-id="39efe-119">En [Windows Diseñador de configuración,](https://www.microsoft.com/store/productId/9NBLGGH4TX22) siga estos cuatro pasos.</span><span class="sxs-lookup"><span data-stu-id="39efe-119">Within [Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) take following four steps.</span></span>

1. <span data-ttu-id="39efe-120">Establezca ApplicationManagement/AllowAllTrustedApps en "Sí".</span><span class="sxs-lookup"><span data-stu-id="39efe-120">Set ApplicationManagement/AllowAllTrustedApps To “Yes”.</span></span> <span data-ttu-id="39efe-121">Vea: [ApplicationManagement/AllowAllTrustedApps](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span><span class="sxs-lookup"><span data-stu-id="39efe-121">See: [ApplicationManagement/AllowAllTrustedApps](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span></span>

2. <span data-ttu-id="39efe-122">Vaya a **UniversalAppInstall**  >  **UserContextAppLicense** y escriba **PackageFamilyName.**</span><span class="sxs-lookup"><span data-stu-id="39efe-122">Navigate to **UniversalAppInstall** > **UserContextAppLicense** enter the **PackageFamilyName**.</span></span> <span data-ttu-id="39efe-123">Vea [UniversalAppInstall](/windows/configuration/wcd/wcd-universalappinstall).</span><span class="sxs-lookup"><span data-stu-id="39efe-123">See [UniversalAppInstall](/windows/configuration/wcd/wcd-universalappinstall).</span></span> <span data-ttu-id="39efe-124">Vea también: [UserContextAppLicense](/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span><span class="sxs-lookup"><span data-stu-id="39efe-124">See also: [UserContextAppLicense](/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span></span>

   <span data-ttu-id="39efe-125">Puede usar Portal de dispositivos en un dispositivo en el que ya haya instalado la aplicación.</span><span class="sxs-lookup"><span data-stu-id="39efe-125">You can use Device Portal on a device you have already installed your app to.</span></span> <span data-ttu-id="39efe-126">Visite la página Aplicaciones y mire la línea PackageRelativeID, toda la información antes de "!" Es **packageFamilyName.**</span><span class="sxs-lookup"><span data-stu-id="39efe-126">Visit the Apps page, and look at the PackageRelativeID line, all the information before the "!" Is your **PackageFamilyName**.</span></span>

3. <span data-ttu-id="39efe-127">A continuación, verá que tiene una nueva sección, **ApplicationFile**.</span><span class="sxs-lookup"><span data-stu-id="39efe-127">You will then see that you have a new section, **ApplicationFile**.</span></span> <span data-ttu-id="39efe-128">Use esta área para cargar el paquete appx.</span><span class="sxs-lookup"><span data-stu-id="39efe-128">Use this area to upload your appx bundle.</span></span>

4. <span data-ttu-id="39efe-129">En función de si ha adquirido la aplicación o ha creado su propia aplicación de LOB, deberá cargar el archivo de licencia o el certificado de seguridad.</span><span class="sxs-lookup"><span data-stu-id="39efe-129">Depending on if you have purchased your app or built your own LOB app, you will need to upload the license file or security certificate.</span></span>

    - <span data-ttu-id="39efe-130">Para el archivo de licencia: vaya a **UniversalAppInstall**  >  **UserContextAppLicence** y vaya a la ubicación de la licencia y cárbala.</span><span class="sxs-lookup"><span data-stu-id="39efe-130">For license file: navigate to **UniversalAppInstall** > **UserContextAppLicence** and browse to the location of your license and upload it.</span></span>
    - <span data-ttu-id="39efe-131">Para el archivo de seguridad, vaya **a Certificados y** seleccione el certificado que desea instalar junto con el paquete .appx.</span><span class="sxs-lookup"><span data-stu-id="39efe-131">For the security file, navigate to **Certificates** and select your certificate to install alongside your .appx bundle.</span></span>

<span data-ttu-id="39efe-132">Asegúrese de guardar el proyecto en una ubicación segura.</span><span class="sxs-lookup"><span data-stu-id="39efe-132">Make sure to save your project to a secure location.</span></span> <span data-ttu-id="39efe-133">A **continuación,** exporte como un paquete **de aprovisionamiento**.</span><span class="sxs-lookup"><span data-stu-id="39efe-133">Then **Export** it as a **Provisioning Package**.</span></span>  

<span data-ttu-id="39efe-134">Consulte también: [Aplicar el paquete de aprovisionamiento a HoloLens](/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span><span class="sxs-lookup"><span data-stu-id="39efe-134">See also: [Apply your provisioning package to HoloLens](/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span></span>
