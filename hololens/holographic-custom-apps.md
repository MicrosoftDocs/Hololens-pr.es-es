---
title: Administrar aplicaciones personalizadas para HoloLens
description: Carga de las aplicaciones personalizadas de la cara en HoloLens. Más información sobre la instalación y desinstalación de aplicaciones holográficas.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 07/01/2019
manager: v-miegge
keywords: hololens, transferencia de archivos, carga de caras, carga de cara, almacén, UWP, aplicación, instalar
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: medium
ms.custom:
- CI 111456
- CSSTroubleshooting
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 12c5eedfab580be8acea48c1fc19b56c1ead08ac
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828865"
---
# <span data-ttu-id="173aa-105">Administrar aplicaciones personalizadas para HoloLens</span><span class="sxs-lookup"><span data-stu-id="173aa-105">Manage custom apps for HoloLens</span></span>

<span data-ttu-id="173aa-106">HoloLens admite muchas aplicaciones existentes de Microsoft Store, así como nuevas aplicaciones creadas específicamente para HoloLens.</span><span class="sxs-lookup"><span data-stu-id="173aa-106">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> <span data-ttu-id="173aa-107">Este artículo se centra en las aplicaciones holográficas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="173aa-107">This article focuses on custom holographic applications.</span></span>  

<span data-ttu-id="173aa-108">Para obtener más información sobre las aplicaciones de la tienda, consulte [Administrar aplicaciones con la tienda](holographic-store-apps.md).</span><span class="sxs-lookup"><span data-stu-id="173aa-108">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

## <span data-ttu-id="173aa-109">Instalar aplicaciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="173aa-109">Install custom apps</span></span>

<span data-ttu-id="173aa-110">Puedes instalar tus propias aplicaciones en HoloLens a través del portal de dispositivos o mediante la implementación de las aplicaciones desde Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="173aa-110">You can install your own applications on HoloLens either by using the Device Portal or by deploying the apps from Visual Studio.</span></span>

### <span data-ttu-id="173aa-111">Instalar un paquete de aplicación con el portal de dispositivos</span><span class="sxs-lookup"><span data-stu-id="173aa-111">Installing an application package with the Device Portal</span></span>

1. <span data-ttu-id="173aa-112">Establece una conexión de [portal de dispositivos](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) al HoloLens de destino.</span><span class="sxs-lookup"><span data-stu-id="173aa-112">Establish a connection from [Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) to the target HoloLens.</span></span>
1. <span data-ttu-id="173aa-113">En el navegación de la izquierda, vaya a la página **aplicaciones** .</span><span class="sxs-lookup"><span data-stu-id="173aa-113">In the left navigation, navigate to the **Apps** page .</span></span>
1. <span data-ttu-id="173aa-114">En el paquete de la **aplicación** , busque el archivo. appx asociado a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="173aa-114">Under **App Package** browse to the .appx file that is associated with your application.</span></span>
   > [!IMPORTANT]
   > <span data-ttu-id="173aa-115">Asegúrese de hacer referencia a los archivos de dependencia y certificados asociados.</span><span class="sxs-lookup"><span data-stu-id="173aa-115">Make sure to reference any associated dependency and certificate files.</span></span>

1. <span data-ttu-id="173aa-116">Seleccione **ir**.</span><span class="sxs-lookup"><span data-stu-id="173aa-116">Select **Go**.</span></span>
   ![Instalar el formulario de aplicaciones en Windows Device portal en Microsoft HoloLens](images/deviceportal-appmanager.jpg)

### <span data-ttu-id="173aa-118">Implementar desde Microsoft Visual Studio 2015</span><span class="sxs-lookup"><span data-stu-id="173aa-118">Deploying from Microsoft Visual Studio 2015</span></span>

1. <span data-ttu-id="173aa-119">Abra la solución de Visual Studio de la aplicación (archivo. sln).</span><span class="sxs-lookup"><span data-stu-id="173aa-119">Open your app's Visual Studio solution (.sln file).</span></span>
1. <span data-ttu-id="173aa-120">Abra las **propiedades**del proyecto.</span><span class="sxs-lookup"><span data-stu-id="173aa-120">Open the project's **Properties**.</span></span>
1. <span data-ttu-id="173aa-121">Seleccione la siguiente configuración de compilación: **principal/x86/máquina remota**.</span><span class="sxs-lookup"><span data-stu-id="173aa-121">Select the following build configuration: **Master/x86/Remote Machine**.</span></span>
1. <span data-ttu-id="173aa-122">Cuando seleccione **equipo remoto**:</span><span class="sxs-lookup"><span data-stu-id="173aa-122">When you select **Remote Machine**:</span></span>
   - <span data-ttu-id="173aa-123">Asegúrese de que la dirección apunta a la dirección IP de Wi-Fi de su HoloLens.</span><span class="sxs-lookup"><span data-stu-id="173aa-123">Make sure the address points to the Wi-Fi IP address of your HoloLens.</span></span>
   - <span data-ttu-id="173aa-124">Configurar la autenticación a **universal (protocolo sin cifrar)**.</span><span class="sxs-lookup"><span data-stu-id="173aa-124">Set authentication to **Universal (Unencrypted Protocol)**.</span></span>
1. <span data-ttu-id="173aa-125">Cree su solución.</span><span class="sxs-lookup"><span data-stu-id="173aa-125">Build your solution.</span></span>
1. <span data-ttu-id="173aa-126">Para implementar la aplicación desde el equipo de desarrollo en HoloLens, seleccione **equipo remoto**.</span><span class="sxs-lookup"><span data-stu-id="173aa-126">To deploy the app from your development PC to your HoloLens, select **Remote Machine**.</span></span> <span data-ttu-id="173aa-127">Si ya tiene una compilación existente en HoloLens, seleccione **sí** para instalar esta versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="173aa-127">If you already have an existing build on the HoloLens, select **Yes** to install this newer version.</span></span>  

   ![Implementación de equipos remotos para aplicaciones a HoloLens de Microsoft en Visual Studio](images/vs2015-remotedeployment.jpg)  
1. <span data-ttu-id="173aa-129">La aplicación se instalará y se iniciará automáticamente en HoloLens.</span><span class="sxs-lookup"><span data-stu-id="173aa-129">The application will install and auto launch on your HoloLens.</span></span>

<span data-ttu-id="173aa-130">Después de instalar una aplicación, la encontrarás en la lista de **todas las aplicaciones** (**iniciar**  >  **todas las aplicaciones**).</span><span class="sxs-lookup"><span data-stu-id="173aa-130">After you've installed an app, you'll find it in the **All apps** list (**Start** > **All apps**).</span></span>
