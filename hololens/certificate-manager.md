---
title: Administrador de certificados
description: Aprende a instalar, administrar y quitar certificados manualmente en dispositivos holoLens 2 de realidad mixta.
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
ms.openlocfilehash: 9d221321adcb8062206695e3e610d35dee14523e
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283691"
---
# <span data-ttu-id="de7d7-103">Administrador de certificados</span><span class="sxs-lookup"><span data-stu-id="de7d7-103">Certificate Manager</span></span>

- <span data-ttu-id="de7d7-104">Herramientas mejoradas de auditoría, diagnóstico y validación para la seguridad y el cumplimiento de dispositivos a través del nuevo Administrador de certificados.</span><span class="sxs-lookup"><span data-stu-id="de7d7-104">Improved auditing, diagnosis, and validation tooling for device security and compliance through the new Certificate Manager.</span></span> <span data-ttu-id="de7d7-105">Esta funcionalidad le permitirá implementar, solucionar problemas y validar los certificados a escala en entornos comerciales.</span><span class="sxs-lookup"><span data-stu-id="de7d7-105">This capability will enable you to deploy, troubleshoot, and validate your certificates at scale in commercial environments.</span></span>

<span data-ttu-id="de7d7-106">En Windows Holographic, versión 20H2, estamos agregando un Administrador de certificados en la aplicación Configuración de HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="de7d7-106">In Windows Holographic, version 20H2, we are adding a Certificate Manager in the HoloLens 2 Settings app.</span></span> <span data-ttu-id="de7d7-107">Vaya a **Configuración > actualizar & seguridad > certificados.**</span><span class="sxs-lookup"><span data-stu-id="de7d7-107">Go to **Settings > Update & Security > Certificates**.</span></span> <span data-ttu-id="de7d7-108">Esta característica proporciona una forma sencilla y fácil de usar para ver, instalar y quitar certificados en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="de7d7-108">This feature provides a simple and user-friendly way to view, install and remove certificates on your device.</span></span> <span data-ttu-id="de7d7-109">Con el nuevo Administrador de certificados, los administradores y usuarios ahora tienen herramientas mejoradas de auditoría, diagnóstico y validación para garantizar que los dispositivos sigan siendo seguros y compatibles.</span><span class="sxs-lookup"><span data-stu-id="de7d7-109">With the new Certificate Manager, admins and users now have improved auditing, diagnosis and validation tooling to ensure that devices remain secure and compliant.</span></span> 

-   <span data-ttu-id="de7d7-110">**Auditoría:** Capacidad para validar que un certificado se implementó correctamente o para confirmar que se quitó correctamente.</span><span class="sxs-lookup"><span data-stu-id="de7d7-110">**Auditing:** Ability to validate that a certificate is deployed correctly or to confirm that it was removed appropriately.</span></span> 
-   <span data-ttu-id="de7d7-111">**Diagnóstico:** Cuando surgen problemas, validar que existen los certificados adecuados en el dispositivo ahorra tiempo y ayuda a solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="de7d7-111">**Diagnosis:** When issues arise, validating that the appropriate certificates exist on the device saves time and helps with troubleshooting.</span></span> 
-   <span data-ttu-id="de7d7-112">**Validación:** Comprobar que un certificado cumple el propósito previsto y es funcional, puede ahorrar mucho tiempo, especialmente en entornos comerciales antes de implementar certificados a mayor escala.</span><span class="sxs-lookup"><span data-stu-id="de7d7-112">**Validation:** Verifying that a certificate serves the intended purpose and is functional, can save significant time, particularly in commercial environments before deploying certificates at larger scale.</span></span>

<span data-ttu-id="de7d7-113">Para buscar rápidamente un certificado específico en la lista, hay opciones para ordenar por nombre, almacén o fecha de expiración.</span><span class="sxs-lookup"><span data-stu-id="de7d7-113">To find a specific certificate in the list quickly, there are options to sort by name, store or expiration date.</span></span> <span data-ttu-id="de7d7-114">Los usuarios también pueden buscar directamente un certificado.</span><span class="sxs-lookup"><span data-stu-id="de7d7-114">Users may also directly search for a certificate.</span></span> <span data-ttu-id="de7d7-115">Para ver propiedades de certificado individuales, seleccione el certificado y haga clic en **Información.**</span><span class="sxs-lookup"><span data-stu-id="de7d7-115">To view individual certificate properties, select the certificate and click on **Info**.</span></span> 

<span data-ttu-id="de7d7-116">La instalación de certificados admite actualmente archivos .cer y .crt.</span><span class="sxs-lookup"><span data-stu-id="de7d7-116">Certificate installation currently supports .cer and .crt files.</span></span> <span data-ttu-id="de7d7-117">Los propietarios de dispositivos pueden instalar certificados en el equipo local y en el usuario actual;  todos los demás usuarios solo pueden instalar en el usuario actual.</span><span class="sxs-lookup"><span data-stu-id="de7d7-117">Device Owners can install certificates in Local Machine and Current User;  all other users can only install into Current User.</span></span> <span data-ttu-id="de7d7-118">Los usuarios solo pueden quitar certificados instalados directamente desde la interfaz de usuario de configuración.</span><span class="sxs-lookup"><span data-stu-id="de7d7-118">Users can only remove certificates installed directly from the Settings UI.</span></span> <span data-ttu-id="de7d7-119">Si un certificado se ha instalado a través de otros medios, también debe quitarse mediante el mismo mecanismo.</span><span class="sxs-lookup"><span data-stu-id="de7d7-119">If a certificate has been installed through other means, it must also be removed by the same mechanism.</span></span>

## <span data-ttu-id="de7d7-120">Para instalar un certificado:</span><span class="sxs-lookup"><span data-stu-id="de7d7-120">To install a certificate:</span></span> 

1.  <span data-ttu-id="de7d7-121">Conecta HoloLens 2 a un equipo.</span><span class="sxs-lookup"><span data-stu-id="de7d7-121">Connect your HoloLens 2 to a PC.</span></span>
1.  <span data-ttu-id="de7d7-122">Coloque el archivo de certificado que desea instalar en una ubicación de HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="de7d7-122">Place the certificate file you want to install in a location on your HoloLens 2.</span></span>
1.  <span data-ttu-id="de7d7-123">Vaya a **Configuración de la aplicación > actualizar & seguridad > certificados**y seleccione Instalar un certificado.</span><span class="sxs-lookup"><span data-stu-id="de7d7-123">Navigate to **Settings App > Update & Security > Certificates**, and select Install a certificate.</span></span>
1.  <span data-ttu-id="de7d7-124">Haga **clic en Importar** archivo y vaya a la ubicación donde guardó el certificado.</span><span class="sxs-lookup"><span data-stu-id="de7d7-124">Click **Import File** and navigate to the location you saved the certificate.</span></span>
1.  <span data-ttu-id="de7d7-125">Seleccione **Ubicación de la tienda.**</span><span class="sxs-lookup"><span data-stu-id="de7d7-125">Select **Store Location**.</span></span>
1.  <span data-ttu-id="de7d7-126">Seleccione **Almacén de certificados.**</span><span class="sxs-lookup"><span data-stu-id="de7d7-126">Select **Certificate Store**.</span></span>
1.  <span data-ttu-id="de7d7-127">Haz clic en **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="de7d7-127">Click **Install**.</span></span>

<span data-ttu-id="de7d7-128">El certificado ahora debe instalarse en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="de7d7-128">The certificate should now be installed on the device.</span></span>

## <span data-ttu-id="de7d7-129">Para quitar un certificado:</span><span class="sxs-lookup"><span data-stu-id="de7d7-129">To remove a certificate:</span></span> 
1. <span data-ttu-id="de7d7-130">Vaya a **Configuración de la aplicación > actualización y seguridad > certificados.**</span><span class="sxs-lookup"><span data-stu-id="de7d7-130">Navigate to **Settings App > Update and Security > Certificates**.</span></span>
1. <span data-ttu-id="de7d7-131">Busque el certificado por su nombre en el cuadro de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="de7d7-131">Search for the certificate by name in the search box.</span></span>
1. <span data-ttu-id="de7d7-132">Seleccione el certificado.</span><span class="sxs-lookup"><span data-stu-id="de7d7-132">Select the certificate.</span></span>
1. <span data-ttu-id="de7d7-133">Haga clic **en Quitar**</span><span class="sxs-lookup"><span data-stu-id="de7d7-133">Click **Remove**</span></span>
1. <span data-ttu-id="de7d7-134">Seleccione **Sí** cuando se le pida confirmación.</span><span class="sxs-lookup"><span data-stu-id="de7d7-134">Select **Yes** when prompted for confirmation.</span></span>


![Visor de certificados en la aplicación Configuración en Ceritifcates](images/certificate-viewer-device.jpg)

![Imagen que muestra cómo usar la interfaz de usuario de certificado para instalar un certificado en Configuración.](images/certificate-device-install.jpg)
