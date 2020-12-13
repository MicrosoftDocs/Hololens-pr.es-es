---
title: Administrar aplicaciones personalizadas para HoloLens
description: Carga de las aplicaciones personalizadas de la cara en HoloLens. Más información sobre la instalación y desinstalación de aplicaciones holográficas.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
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
ms.openlocfilehash: 67a857eb35126435f5642ee60168128300401394
ms.sourcegitcommit: cd2071c12eaabe46c829b53c22d13e21b8af5b53
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2020
ms.locfileid: "11218637"
---
# <span data-ttu-id="e93c7-105">Administrar aplicaciones personalizadas para HoloLens</span><span class="sxs-lookup"><span data-stu-id="e93c7-105">Manage custom apps for HoloLens</span></span>

<span data-ttu-id="e93c7-106">HoloLens soporta muchas aplicaciones existentes de Microsoft Store, así como nuevas aplicaciones construidas específicamente para HoloLens.</span><span class="sxs-lookup"><span data-stu-id="e93c7-106">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> <span data-ttu-id="e93c7-107">Este artículo se centra en las aplicaciones holográficas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="e93c7-107">This article focuses on custom holographic applications.</span></span>  

<span data-ttu-id="e93c7-108">Para obtener más información sobre las aplicaciones de la tienda, consulte [Administrar aplicaciones con la tienda](holographic-store-apps.md).</span><span class="sxs-lookup"><span data-stu-id="e93c7-108">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e93c7-109">La siguiente información se creó para HoloLens (1ª generación), también llamada la edición para desarrolladores de HoloLens en ese momento.</span><span class="sxs-lookup"><span data-stu-id="e93c7-109">The following information was created for the HoloLens (1st gen), also called the HoloLens Developer Edition at the time.</span></span> <span data-ttu-id="e93c7-110">Ya que estas aplicaciones de instalación de prueba a través del portal de dispositivos y la instalación de aplicaciones a través de Visual Studio eran comunes.</span><span class="sxs-lookup"><span data-stu-id="e93c7-110">As such sideloading apps via device portal and installing apps via Visual Studio were commonplace then.</span></span> <span data-ttu-id="e93c7-111">Para las implementaciones empresariales, no se recomienda habilitar el modo de desarrollador, que usan ambos métodos.</span><span class="sxs-lookup"><span data-stu-id="e93c7-111">For enterprise deployments we do not recommend enabling Developer Mode, which both of these methods use.</span></span> <span data-ttu-id="e93c7-112">Si estás interesado en un método seguro de implementación de aplicaciones, consulta la [información general sobre la administración de aplicaciones:](app-deploy-overview.md)</span><span class="sxs-lookup"><span data-stu-id="e93c7-112">If you are interested in a secure app deployment method please review our [App Management: Overview](app-deploy-overview.md).</span></span>
>
> <span data-ttu-id="e93c7-113">Si busca el método de desarrollador de instalación de aplicaciones para dispositivos HoloLens 2, consulte:</span><span class="sxs-lookup"><span data-stu-id="e93c7-113">If you are looking for either developer method of app installation for HoloLens 2 devices please refer to:</span></span>
> - [<span data-ttu-id="e93c7-114">Portal de dispositivos: instalación de una aplicación</span><span class="sxs-lookup"><span data-stu-id="e93c7-114">Device Portal: Installing an App</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [<span data-ttu-id="e93c7-115">Usar Visual Studio para implementar y depurar aplicaciones</span><span class="sxs-lookup"><span data-stu-id="e93c7-115">Using Visual Studio to deploy and debug Apps</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <span data-ttu-id="e93c7-116">Instalar aplicaciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="e93c7-116">Install custom apps</span></span>

<span data-ttu-id="e93c7-117">Puedes instalar tus propias aplicaciones en HoloLens a través del portal de dispositivos o mediante la implementación de las aplicaciones desde Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e93c7-117">You can install your own applications on HoloLens either by using the Device Portal or by deploying the apps from Visual Studio.</span></span>

### <span data-ttu-id="e93c7-118">Instalar un paquete de aplicación con el portal de dispositivos</span><span class="sxs-lookup"><span data-stu-id="e93c7-118">Installing an application package with the Device Portal</span></span>

1. <span data-ttu-id="e93c7-119">Establece una conexión de [portal de dispositivos](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) al HoloLens de destino.</span><span class="sxs-lookup"><span data-stu-id="e93c7-119">Establish a connection from [Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) to the target HoloLens.</span></span>
1. <span data-ttu-id="e93c7-120">En el navegación de la izquierda, vaya a la página **aplicaciones** .</span><span class="sxs-lookup"><span data-stu-id="e93c7-120">In the left navigation, navigate to the **Apps** page .</span></span>
1. <span data-ttu-id="e93c7-121">En el paquete de la **aplicación** , busque el archivo. appx asociado a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e93c7-121">Under **App Package** browse to the .appx file that is associated with your application.</span></span>
   > [!IMPORTANT]
   > <span data-ttu-id="e93c7-122">Asegúrese de hacer referencia a los archivos de dependencia y certificados asociados.</span><span class="sxs-lookup"><span data-stu-id="e93c7-122">Make sure to reference any associated dependency and certificate files.</span></span>

1. <span data-ttu-id="e93c7-123">Seleccione **ir**.</span><span class="sxs-lookup"><span data-stu-id="e93c7-123">Select **Go**.</span></span>
   ![Instalar el formulario de aplicaciones en Windows Device portal en Microsoft HoloLens](images/deviceportal-appmanager.jpg)

### <span data-ttu-id="e93c7-125">Implementar desde Microsoft Visual Studio 2015</span><span class="sxs-lookup"><span data-stu-id="e93c7-125">Deploying from Microsoft Visual Studio 2015</span></span>

1. <span data-ttu-id="e93c7-126">Abra la solución de Visual Studio de la aplicación (archivo. sln).</span><span class="sxs-lookup"><span data-stu-id="e93c7-126">Open your app's Visual Studio solution (.sln file).</span></span>
1. <span data-ttu-id="e93c7-127">Abra las **propiedades**del proyecto.</span><span class="sxs-lookup"><span data-stu-id="e93c7-127">Open the project's **Properties**.</span></span>
1. <span data-ttu-id="e93c7-128">Seleccione la siguiente configuración de compilación: **principal/x86/máquina remota**.</span><span class="sxs-lookup"><span data-stu-id="e93c7-128">Select the following build configuration: **Master/x86/Remote Machine**.</span></span>
1. <span data-ttu-id="e93c7-129">Cuando seleccione **equipo remoto**:</span><span class="sxs-lookup"><span data-stu-id="e93c7-129">When you select **Remote Machine**:</span></span>
   - <span data-ttu-id="e93c7-130">Asegúrese de que la dirección apunta a la dirección IP Wi-Fi de su HoloLens.</span><span class="sxs-lookup"><span data-stu-id="e93c7-130">Make sure the address points to the Wi-Fi IP address of your HoloLens.</span></span>
   - <span data-ttu-id="e93c7-131">Configurar la autenticación a **universal (protocolo sin cifrar)**.</span><span class="sxs-lookup"><span data-stu-id="e93c7-131">Set authentication to **Universal (Unencrypted Protocol)**.</span></span>
1. <span data-ttu-id="e93c7-132">Cree su solución.</span><span class="sxs-lookup"><span data-stu-id="e93c7-132">Build your solution.</span></span>
1. <span data-ttu-id="e93c7-133">Para implementar la aplicación desde el equipo de desarrollo en HoloLens, seleccione **equipo remoto**.</span><span class="sxs-lookup"><span data-stu-id="e93c7-133">To deploy the app from your development PC to your HoloLens, select **Remote Machine**.</span></span> <span data-ttu-id="e93c7-134">Si ya tiene una compilación existente en HoloLens, seleccione **sí** para instalar esta versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="e93c7-134">If you already have an existing build on the HoloLens, select **Yes** to install this newer version.</span></span>  

   ![Implementación de equipos remotos para aplicaciones a HoloLens de Microsoft en Visual Studio](images/vs2015-remotedeployment.jpg)  
1. <span data-ttu-id="e93c7-136">La aplicación se instalará y se iniciará automáticamente en HoloLens.</span><span class="sxs-lookup"><span data-stu-id="e93c7-136">The application will install and auto launch on your HoloLens.</span></span>

<span data-ttu-id="e93c7-137">Después de instalar una aplicación, la encontrarás en la lista de **todas las aplicaciones** (**iniciar**  >  **todas las aplicaciones**).</span><span class="sxs-lookup"><span data-stu-id="e93c7-137">After you've installed an app, you'll find it in the **All apps** list (**Start** > **All apps**).</span></span>
