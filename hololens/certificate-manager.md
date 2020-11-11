---
title: Administrador de certificados
description: Más información sobre la administración de certificados manualmente en HoloLens 2.
author: evmill
ms.author: v-evmill
manager: yannisle
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 04d7e8cb78357b5398c58e0a0c55e6e530fa363a
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163230"
---
# <span data-ttu-id="c6051-103">Administrador de certificados</span><span class="sxs-lookup"><span data-stu-id="c6051-103">Certificate Manager</span></span>

- <span data-ttu-id="c6051-104">Auditoría, diagnóstico y herramientas de validación mejoradas para la seguridad y el cumplimiento de los dispositivos a través del nuevo administrador de certificados.</span><span class="sxs-lookup"><span data-stu-id="c6051-104">Improved auditing, diagnosis, and validation tooling for device security and compliance through the new Certificate Manager.</span></span> <span data-ttu-id="c6051-105">Esta capacidad le permitirá implementar, solucionar problemas y validar sus certificados a escala en entornos comerciales.</span><span class="sxs-lookup"><span data-stu-id="c6051-105">This capability will enable you to deploy, troubleshoot, and validate your certificates at scale in commercial environments.</span></span>

<span data-ttu-id="c6051-106">En Windows Holographic, versión 20H2, agregamos un administrador de certificados en la aplicación de configuración de HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="c6051-106">In Windows Holographic, version 20H2, we are adding a Certificate Manager in the HoloLens 2 Settings app.</span></span> <span data-ttu-id="c6051-107">Vaya a **configuración > actualizar & certificados > de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="c6051-107">Go to **Settings > Update & Security > Certificates**.</span></span> <span data-ttu-id="c6051-108">Esta característica proporciona una forma sencilla y fácil de usar para ver, instalar y quitar certificados en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c6051-108">This feature provides a simple and user-friendly way to view, install and remove certificates on your device.</span></span> <span data-ttu-id="c6051-109">Con el nuevo administrador de certificados, los administradores y los usuarios han mejorado las herramientas de auditoría, diagnóstico y validación para asegurarse de que los dispositivos siguen siendo seguros y cumplen con las normas.</span><span class="sxs-lookup"><span data-stu-id="c6051-109">With the new Certificate Manager, admins and users now have improved auditing, diagnosis and validation tooling to ensure that devices remain secure and compliant.</span></span> 

-   <span data-ttu-id="c6051-110">**Auditoría:** Posibilidad de validar que un certificado se ha implementado correctamente o para confirmar que se ha eliminado correctamente.</span><span class="sxs-lookup"><span data-stu-id="c6051-110">**Auditing:** Ability to validate that a certificate is deployed correctly or to confirm that it was removed appropriately.</span></span> 
-   <span data-ttu-id="c6051-111">**Diagnóstico:** Cuando surjan problemas, validar que los certificados adecuados existen en el dispositivo ahorra tiempo y ayuda con la solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="c6051-111">**Diagnosis:** When issues arise, validating that the appropriate certificates exist on the device saves time and helps with troubleshooting.</span></span> 
-   <span data-ttu-id="c6051-112">**Validación:** Comprobar que un certificado tiene el propósito pretendido y es funcional, puede ahorrar mucho tiempo, especialmente en entornos comerciales antes de implementar certificados a mayor escala.</span><span class="sxs-lookup"><span data-stu-id="c6051-112">**Validation:** Verifying that a certificate serves the intended purpose and is functional, can save significant time, particularly in commercial environments before deploying certificates at larger scale.</span></span>

<span data-ttu-id="c6051-113">Para buscar rápidamente un certificado específico en la lista, hay opciones para ordenar por nombre, almacén o fecha de expiración.</span><span class="sxs-lookup"><span data-stu-id="c6051-113">To find a specific certificate in the list quickly, there are options to sort by name, store or expiration date.</span></span> <span data-ttu-id="c6051-114">Los usuarios también pueden buscar un certificado directamente.</span><span class="sxs-lookup"><span data-stu-id="c6051-114">Users may also directly search for a certificate.</span></span> <span data-ttu-id="c6051-115">Para ver las propiedades de certificado individuales, seleccione el certificado y haga clic en **información**.</span><span class="sxs-lookup"><span data-stu-id="c6051-115">To view individual certificate properties, select the certificate and click on **Info**.</span></span> 

<span data-ttu-id="c6051-116">La instalación de certificados admite actualmente archivos. cer y. CRT.</span><span class="sxs-lookup"><span data-stu-id="c6051-116">Certificate installation currently supports .cer and .crt files.</span></span> <span data-ttu-id="c6051-117">Los propietarios de dispositivos pueden instalar certificados en la máquina local y en el usuario actual;  el resto de los usuarios solo pueden instalarse en el usuario actual.</span><span class="sxs-lookup"><span data-stu-id="c6051-117">Device Owners can install certificates in Local Machine and Current User;  all other users can only install into Current User.</span></span> <span data-ttu-id="c6051-118">Los usuarios solo pueden quitar certificados instalados directamente desde la interfaz de usuario de configuración.</span><span class="sxs-lookup"><span data-stu-id="c6051-118">Users can only remove certificates installed directly from the Settings UI.</span></span> <span data-ttu-id="c6051-119">Si se ha instalado un certificado por otros medios, también debe ser eliminado por el mismo mecanismo.</span><span class="sxs-lookup"><span data-stu-id="c6051-119">If a certificate has been installed through other means, it must also be removed by the same mechanism.</span></span>

## <span data-ttu-id="c6051-120">Para instalar un certificado:</span><span class="sxs-lookup"><span data-stu-id="c6051-120">To install a certificate:</span></span> 

1.  <span data-ttu-id="c6051-121">Conecta tu HoloLens 2 a un equipo PC.</span><span class="sxs-lookup"><span data-stu-id="c6051-121">Connect your HoloLens 2 to a PC.</span></span>
1.  <span data-ttu-id="c6051-122">Coloca el archivo de certificado que deseas instalar en una ubicación de tu HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="c6051-122">Place the certificate file you want to install in a location on your HoloLens 2.</span></span>
1.  <span data-ttu-id="c6051-123">Vaya a **configuración de la aplicación > actualizar & certificados > de seguridad**y seleccione instalar un certificado.</span><span class="sxs-lookup"><span data-stu-id="c6051-123">Navigate to **Settings App > Update & Security > Certificates**, and select Install a certificate.</span></span>
1.  <span data-ttu-id="c6051-124">Haga clic en **Importar archivo** y vaya a la ubicación donde guardó el certificado.</span><span class="sxs-lookup"><span data-stu-id="c6051-124">Click **Import File** and navigate to the location you saved the certificate.</span></span>
1.  <span data-ttu-id="c6051-125">Seleccione **Ubicación**de la tienda.</span><span class="sxs-lookup"><span data-stu-id="c6051-125">Select **Store Location**.</span></span>
1.  <span data-ttu-id="c6051-126">Seleccione **almacén de certificados**.</span><span class="sxs-lookup"><span data-stu-id="c6051-126">Select **Certificate Store**.</span></span>
1.  <span data-ttu-id="c6051-127">Haz clic en **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="c6051-127">Click **Install**.</span></span>

<span data-ttu-id="c6051-128">El certificado debe instalarse ahora en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c6051-128">The certificate should now be installed on the device.</span></span>

## <span data-ttu-id="c6051-129">Para quitar un certificado:</span><span class="sxs-lookup"><span data-stu-id="c6051-129">To remove a certificate:</span></span> 
1. <span data-ttu-id="c6051-130">Vaya a **configuración > la actualización y los certificados de > de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="c6051-130">Navigate to **Settings App > Update and Security > Certificates**.</span></span>
1. <span data-ttu-id="c6051-131">Busque el certificado por el nombre en el cuadro de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="c6051-131">Search for the certificate by name in the search box.</span></span>
1. <span data-ttu-id="c6051-132">Seleccione el certificado.</span><span class="sxs-lookup"><span data-stu-id="c6051-132">Select the certificate.</span></span>
1. <span data-ttu-id="c6051-133">Haga clic en **quitar**</span><span class="sxs-lookup"><span data-stu-id="c6051-133">Click **Remove**</span></span>
1. <span data-ttu-id="c6051-134">Seleccione **sí** cuando se le solicite confirmación.</span><span class="sxs-lookup"><span data-stu-id="c6051-134">Select **Yes** when prompted for confirmation.</span></span>


![Visor de certificados de la aplicación configuración en CERITIFCATES](images/certificate-viewer-device.jpg)

![Imagen que muestra cómo usar la interfaz de usuario de certificado para instalar un certificado en configuración.](images/certificate-device-install.jpg)
