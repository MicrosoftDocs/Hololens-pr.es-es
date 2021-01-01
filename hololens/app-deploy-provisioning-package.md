---
title: Paquete de aprovisionamiento
description: aplicación, implementación de aplicaciones, implementación de aplicaciones empresariales, aprovisionamiento
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
ms.openlocfilehash: 11bc83be188e1b81959690efcb2bdf26d800aae3
ms.sourcegitcommit: fc268335e5df529a1cedc2c6b88fa86245fe1b9b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/31/2020
ms.locfileid: "11252681"
---
# <span data-ttu-id="6ca01-104">Paquete de aprovisionamiento</span><span class="sxs-lookup"><span data-stu-id="6ca01-104">Provisioning Package</span></span>

<span data-ttu-id="6ca01-105">Los paquetes de aprovisionamiento se pueden usar para preparar y configurar dispositivos en un entorno sin acceso a administración de extremos.</span><span class="sxs-lookup"><span data-stu-id="6ca01-105">Provisioning packages can be used to prepare and configure devices in an environment without access to endpoint management.</span></span> <span data-ttu-id="6ca01-106">También se pueden implementar en un dispositivo, independientemente de la identidad del usuario, el estado de inscripción, durante la configuración rápida (OOBE) o [aplicando un paquete de aprovisionamiento durante la configuración](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).</span><span class="sxs-lookup"><span data-stu-id="6ca01-106">They can also be deployed to a device regardless of identity of the user, enrollment status, during the Out of Box Experience (OOBE), or by [applying a provisioning package during setup](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).</span></span>

## <span data-ttu-id="6ca01-107">Consideraciones sobre los paquetes de aprovisionamiento:</span><span class="sxs-lookup"><span data-stu-id="6ca01-107">Provisioning Packages considerations:</span></span>

* <span data-ttu-id="6ca01-108">Aplicaciones no públicas</span><span class="sxs-lookup"><span data-stu-id="6ca01-108">Non-Public apps</span></span>
* <span data-ttu-id="6ca01-109">Solo carga del lado USB</span><span class="sxs-lookup"><span data-stu-id="6ca01-109">USB side-load only</span></span>
* <span data-ttu-id="6ca01-110">No hay ninguna actualización automática (requiere actualizaciones manuales a través de PPKGs)</span><span class="sxs-lookup"><span data-stu-id="6ca01-110">No auto update (requires manual updates via PPKGs)</span></span>

<span data-ttu-id="6ca01-111">Las aplicaciones instaladas a través de un paquete de aprovisionamiento deben estar firmadas por un certificado del almacén de la máquina local.</span><span class="sxs-lookup"><span data-stu-id="6ca01-111">Apps installed via a provisioning package must be signed by a certificate in the local machine store.</span></span> <span data-ttu-id="6ca01-112">Los paquetes de aprovisionamiento solo pueden instalar certificados en el almacén del dispositivo (equipo local), por lo tanto, una aplicación y un certificado se pueden instalar a través del mismo paquete de aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="6ca01-112">Provisioning packages can only install certificates to the device (local machine) store, therefore an app and certificate may be installed via the same provisioning package.</span></span> <span data-ttu-id="6ca01-113">Si va a implementar su certificado desde MDM o mediante el administrador de [certificados](certificate-manager.md), asegúrese de implementar el certificado en el almacén de la máquina local para firmar las aplicaciones instaladas de esta manera.</span><span class="sxs-lookup"><span data-stu-id="6ca01-113">If you are deploying your certificate from MDM or installing via the [Certificate Manager](certificate-manager.md), make sure to deploy the certificate to the local machine store to sign apps installed this way.</span></span>

<span data-ttu-id="6ca01-114">Para obtener información sobre los conceptos básicos de la creación de un paquete de aprovisionamiento para dispositivos HoloLens, visite la [configuración de hololens](https://docs.microsoft.com/hololens/hololens-provisioning).</span><span class="sxs-lookup"><span data-stu-id="6ca01-114">To learn the basics of creating a Provisioning Package for HoloLens devices, visit [HoloLens Provisioning](https://docs.microsoft.com/hololens/hololens-provisioning).</span></span> <span data-ttu-id="6ca01-115">Para implementar una aplicación, debe empezar con el aprovisionamiento avanzado.</span><span class="sxs-lookup"><span data-stu-id="6ca01-115">To deploy an app, you must start with advanced provisioning.</span></span>

> [!NOTE]
> <span data-ttu-id="6ca01-116">HoloLens (1º gen) tiene un soporte limitado para instalar aplicaciones (**UniversalAppInstall**) mediante un paquete de aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="6ca01-116">HoloLens (1st gen) has limited support installing apps (**UniversalAppInstall**) by using a provisioning package.</span></span> <span data-ttu-id="6ca01-117">Los dispositivos HoloLens (1. ª gen) solo admiten la instalación de una aplicación a través de PPKG solo durante OOBE y solo con instalaciones de contexto de usuario.</span><span class="sxs-lookup"><span data-stu-id="6ca01-117">HoloLens (1st gen) devices only support installing an app via PPKG only during OOBE and only with user context installs.</span></span>

## <span data-ttu-id="6ca01-118">Programa de instalación</span><span class="sxs-lookup"><span data-stu-id="6ca01-118">Setup</span></span>

<span data-ttu-id="6ca01-119">En el [Diseñador de configuración de Windows](https://www.microsoft.com/store/productId/9NBLGGH4TX22) , siga estos cuatro pasos.</span><span class="sxs-lookup"><span data-stu-id="6ca01-119">Within [Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) take following four steps.</span></span>

1. <span data-ttu-id="6ca01-120">Establece ApplicationManagement/AllowAllTrustedApps en "sí".</span><span class="sxs-lookup"><span data-stu-id="6ca01-120">Set ApplicationManagement/AllowAllTrustedApps To “Yes”.</span></span> <span data-ttu-id="6ca01-121">Consulte: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span><span class="sxs-lookup"><span data-stu-id="6ca01-121">See: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span></span>

2. <span data-ttu-id="6ca01-122">Vaya a **UniversalAppInstall**  >  **UserContextAppLicense** ingrese el **PackageFamilyName**.</span><span class="sxs-lookup"><span data-stu-id="6ca01-122">Navigate to **UniversalAppInstall** > **UserContextAppLicense** enter the **PackageFamilyName**.</span></span> <span data-ttu-id="6ca01-123">Consulta [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall).</span><span class="sxs-lookup"><span data-stu-id="6ca01-123">See [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall).</span></span> <span data-ttu-id="6ca01-124">Vea también: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span><span class="sxs-lookup"><span data-stu-id="6ca01-124">See also: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span></span>

   <span data-ttu-id="6ca01-125">Puede usar Device portal en un dispositivo en el que ya haya instalado la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6ca01-125">You can use Device Portal on a device you have already installed your app to.</span></span> <span data-ttu-id="6ca01-126">Visite la página aplicaciones y mire la línea PackageRelativeID, toda la información antes de la "!" Es tu **PackageFamilyName**.</span><span class="sxs-lookup"><span data-stu-id="6ca01-126">Visit the Apps page, and look at the PackageRelativeID line, all the information before the "!" Is your **PackageFamilyName**.</span></span>

3. <span data-ttu-id="6ca01-127">Verá que tiene una nueva sección, **ApplicationFile**.</span><span class="sxs-lookup"><span data-stu-id="6ca01-127">You will then see that you have a new section, **ApplicationFile**.</span></span> <span data-ttu-id="6ca01-128">Usa este área para cargar tu paquete appx.</span><span class="sxs-lookup"><span data-stu-id="6ca01-128">Use this area to upload your appx bundle.</span></span>

4. <span data-ttu-id="6ca01-129">En función de si ha comprado la aplicación o ha creado su propia aplicación de LOB, tendrá que cargar el archivo de licencia o el certificado de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6ca01-129">Depending on if you have purchased your app or built your own LOB app, you will need to upload the license file or security certificate.</span></span>

    - <span data-ttu-id="6ca01-130">Para el archivo de licencia: vaya a **UniversalAppInstall**  >  **UserContextAppLicence** y vaya a la ubicación de su licencia y cargarla.</span><span class="sxs-lookup"><span data-stu-id="6ca01-130">For license file: navigate to **UniversalAppInstall** > **UserContextAppLicence** and browse to the location of your license and upload it.</span></span>
    - <span data-ttu-id="6ca01-131">Para el archivo de seguridad, navegue hasta **certificados** y seleccione el certificado para instalar junto a su paquete. appx.</span><span class="sxs-lookup"><span data-stu-id="6ca01-131">For the security file, navigate to **Certificates** and select your certificate to install alongside your .appx bundle.</span></span>

<span data-ttu-id="6ca01-132">Asegúrese de guardar el proyecto en una ubicación segura.</span><span class="sxs-lookup"><span data-stu-id="6ca01-132">Make sure to save your project to a secure location.</span></span> <span data-ttu-id="6ca01-133">A continuación, **expórtelo** como un **paquete de aprovisionamiento**.</span><span class="sxs-lookup"><span data-stu-id="6ca01-133">Then **Export** it as a **Provisioning Package**.</span></span>  

<span data-ttu-id="6ca01-134">Consulte también: [aplicar el paquete de aprovisionamiento a HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span><span class="sxs-lookup"><span data-stu-id="6ca01-134">See also: [Apply your provisioning package to HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span></span>
