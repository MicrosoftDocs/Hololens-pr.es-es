---
title: Administrar aplicaciones personalizadas para HoloLens (1.ª generación)
description: Aprende a instalar, desinstalar y cargar aplicaciones holográficas personalizadas en dispositivos HoloLens con Device Portal y Visual Studio.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: hololens, instalación de prueba, instalación de prueba, side load, side-load, side-load, tienda, uwp, aplicación, instalar
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
ms.openlocfilehash: 721c169c8ad34acab6914448af8ffc6ceec97a0e
ms.sourcegitcommit: 4c6d982bee72195bef955532738711f2b00ac8be
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "11296993"
---
# <span data-ttu-id="8ca43-104">Administrar aplicaciones personalizadas para HoloLens (1.ª generación)</span><span class="sxs-lookup"><span data-stu-id="8ca43-104">Manage custom apps for HoloLens (1st gen)</span></span>

<span data-ttu-id="8ca43-105">HoloLens soporta muchas aplicaciones existentes de Microsoft Store, así como nuevas aplicaciones construidas específicamente para HoloLens.</span><span class="sxs-lookup"><span data-stu-id="8ca43-105">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> <span data-ttu-id="8ca43-106">Este artículo se centra en aplicaciones holográficas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="8ca43-106">This article focuses on custom holographic applications.</span></span>  

<span data-ttu-id="8ca43-107">Para obtener más información acerca de las aplicaciones de la Tienda, consulta [Administrar aplicaciones con la tienda.](holographic-store-apps.md)</span><span class="sxs-lookup"><span data-stu-id="8ca43-107">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8ca43-108">La siguiente información se creó para HoloLens (1.ª generación), también denominada HoloLens Developer Edition en ese momento.</span><span class="sxs-lookup"><span data-stu-id="8ca43-108">The following information was created for the HoloLens (1st gen), also called the HoloLens Developer Edition at the time.</span></span> <span data-ttu-id="8ca43-109">Por lo tanto, la instalación local de aplicaciones a través del portal de dispositivos y la instalación de aplicaciones Visual Studio era habitual en ese momento.</span><span class="sxs-lookup"><span data-stu-id="8ca43-109">As such sideloading apps via device portal and installing apps via Visual Studio were commonplace then.</span></span> <span data-ttu-id="8ca43-110">Para las implementaciones empresariales no recomendamos habilitar el modo de desarrollador, que usan ambos métodos.</span><span class="sxs-lookup"><span data-stu-id="8ca43-110">For enterprise deployments we do not recommend enabling Developer Mode, which both of these methods use.</span></span> <span data-ttu-id="8ca43-111">Si está interesado en un método seguro de implementación de aplicaciones, revise nuestra administración [de aplicaciones: Información general.](app-deploy-overview.md)</span><span class="sxs-lookup"><span data-stu-id="8ca43-111">If you are interested in a secure app deployment method please review our [App Management: Overview](app-deploy-overview.md).</span></span>
>
> <span data-ttu-id="8ca43-112">Si está buscando cualquiera de los métodos de instalación de aplicaciones para dispositivos HoloLens 2, consulte:</span><span class="sxs-lookup"><span data-stu-id="8ca43-112">If you are looking for either developer method of app installation for HoloLens 2 devices please refer to:</span></span>
> - [<span data-ttu-id="8ca43-113">Device Portal: Instalar una aplicación</span><span class="sxs-lookup"><span data-stu-id="8ca43-113">Device Portal: Installing an App</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [<span data-ttu-id="8ca43-114">Usar Visual Studio para implementar y depurar aplicaciones</span><span class="sxs-lookup"><span data-stu-id="8ca43-114">Using Visual Studio to deploy and debug Apps</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <span data-ttu-id="8ca43-115">Instalar aplicaciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="8ca43-115">Install custom apps</span></span>

<span data-ttu-id="8ca43-116">Puedes instalar tus propias aplicaciones en HoloLens mediante Device Portal o implementando las aplicaciones desde Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="8ca43-116">You can install your own applications on HoloLens either by using the Device Portal or by deploying the apps from Visual Studio.</span></span>

### <span data-ttu-id="8ca43-117">Instalación de un paquete de aplicación con Device Portal</span><span class="sxs-lookup"><span data-stu-id="8ca43-117">Installing an application package with the Device Portal</span></span>

1. <span data-ttu-id="8ca43-118">Establecer una conexión desde [Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) al HoloLens de destino.</span><span class="sxs-lookup"><span data-stu-id="8ca43-118">Establish a connection from [Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) to the target HoloLens.</span></span>

1. <span data-ttu-id="8ca43-119">En el panel de navegación izquierdo, vaya a la **página** Aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="8ca43-119">In the left navigation, navigate to the **Apps** page.</span></span>

1. <span data-ttu-id="8ca43-120">En **Paquete de la** aplicación, busca el archivo .appx asociado a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8ca43-120">Under **App Package** browse to the .appx file that is associated with your application.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="8ca43-121">Asegúrate de hacer referencia a cualquier archivo de certificado y dependencia asociado.</span><span class="sxs-lookup"><span data-stu-id="8ca43-121">Make sure to reference any associated dependency and certificate files.</span></span>

1. <span data-ttu-id="8ca43-122">Seleccione **Ir**.</span><span class="sxs-lookup"><span data-stu-id="8ca43-122">Select **Go**.</span></span>

   > [!div class="mx-imgBorder"]
   > ![Instalar el formulario de aplicación en Windows Device Portal en Microsoft HoloLens](images/deviceportal-appmanager.jpg)

### <span data-ttu-id="8ca43-124">Implementación desde Microsoft Visual Studio 2015</span><span class="sxs-lookup"><span data-stu-id="8ca43-124">Deploying from Microsoft Visual Studio 2015</span></span>

1. <span data-ttu-id="8ca43-125">Abre la solución de Visual Studio aplicación (archivo .sln).</span><span class="sxs-lookup"><span data-stu-id="8ca43-125">Open your app's Visual Studio solution (.sln file).</span></span>

1. <span data-ttu-id="8ca43-126">Abra las propiedades del **proyecto.**</span><span class="sxs-lookup"><span data-stu-id="8ca43-126">Open the project's **Properties**.</span></span>

1. <span data-ttu-id="8ca43-127">Seleccione la siguiente configuración de compilación: **Maestro/x86/Máquina remota.**</span><span class="sxs-lookup"><span data-stu-id="8ca43-127">Select the following build configuration: **Master/x86/Remote Machine**.</span></span>

1. <span data-ttu-id="8ca43-128">Al seleccionar Equipo **remoto:**</span><span class="sxs-lookup"><span data-stu-id="8ca43-128">When you select **Remote Machine**:</span></span>
   - <span data-ttu-id="8ca43-129">Asegúrese de que la dirección apunta a la Wi-Fi IP de su HoloLens.</span><span class="sxs-lookup"><span data-stu-id="8ca43-129">Make sure the address points to the Wi-Fi IP address of your HoloLens.</span></span>
   - <span data-ttu-id="8ca43-130">Establezca la **autenticación en Universal (protocolo sin cifrar).**</span><span class="sxs-lookup"><span data-stu-id="8ca43-130">Set authentication to **Universal (Unencrypted Protocol)**.</span></span>
   
1. <span data-ttu-id="8ca43-131">Cree la solución.</span><span class="sxs-lookup"><span data-stu-id="8ca43-131">Build your solution.</span></span>

1. <span data-ttu-id="8ca43-132">Para implementar la aplicación desde el equipo de desarrollo a HoloLens, selecciona **Máquina remota.**</span><span class="sxs-lookup"><span data-stu-id="8ca43-132">To deploy the app from your development PC to your HoloLens, select **Remote Machine**.</span></span> <span data-ttu-id="8ca43-133">Si ya tienes una compilación existente en HoloLens, selecciona **Sí** para instalar esta versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="8ca43-133">If you already have an existing build on the HoloLens, select **Yes** to install this newer version.</span></span>  

   ![Implementación de máquina remota para aplicaciones en Microsoft HoloLens en Visual Studio](images/vs2015-remotedeployment.jpg)  
   
1. <span data-ttu-id="8ca43-135">La aplicación se instalará y se iniciará automáticamente en holoLens.</span><span class="sxs-lookup"><span data-stu-id="8ca43-135">The application will install and auto launch on your HoloLens.</span></span>

<span data-ttu-id="8ca43-136">Después de instalar una aplicación, la encontrarás en \*\*\*\* la lista Todas las aplicaciones **(Iniciar**  >  **todas las aplicaciones).**</span><span class="sxs-lookup"><span data-stu-id="8ca43-136">After you've installed an app, you'll find it in the **All apps** list (**Start** > **All apps**).</span></span>
