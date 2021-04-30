---
title: Administración de aplicaciones personalizadas para HoloLens (1ª generación)
description: Obtenga información sobre cómo instalar, desinstalar y cargar aplicaciones holográficas personalizadas en dispositivos HoloLens mediante Portal de dispositivos y Visual Studio.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: hololens, sideload, side load, side-load, store, uwp, app, install
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2021
ms.locfileid: "108310115"
---
# <a name="manage-custom-apps-for-hololens-1st-gen"></a><span data-ttu-id="2eafc-104">Administración de aplicaciones personalizadas para HoloLens (1ª generación)</span><span class="sxs-lookup"><span data-stu-id="2eafc-104">Manage custom apps for HoloLens (1st gen)</span></span>

<span data-ttu-id="2eafc-105">HoloLens admite muchas aplicaciones existentes del Microsoft Store, así como nuevas aplicaciones creadas específicamente para HoloLens.</span><span class="sxs-lookup"><span data-stu-id="2eafc-105">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> <span data-ttu-id="2eafc-106">Este artículo se centra en aplicaciones holográficas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="2eafc-106">This article focuses on custom holographic applications.</span></span>  

<span data-ttu-id="2eafc-107">Para obtener más información sobre las aplicaciones de la tienda, [vea Administrar aplicaciones con la tienda](holographic-store-apps.md).</span><span class="sxs-lookup"><span data-stu-id="2eafc-107">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2eafc-108">La siguiente información se creó para HoloLens (1.ª generación), también denominada HoloLens Developer Edition en ese momento.</span><span class="sxs-lookup"><span data-stu-id="2eafc-108">The following information was created for the HoloLens (1st gen), also called the HoloLens Developer Edition at the time.</span></span> <span data-ttu-id="2eafc-109">Por lo tanto, la instalación local de aplicaciones a través del portal de dispositivos y la instalación de Visual Studio eran habituales en ese momento.</span><span class="sxs-lookup"><span data-stu-id="2eafc-109">As such sideloading apps via device portal and installing apps via Visual Studio were commonplace then.</span></span> <span data-ttu-id="2eafc-110">En el caso de las implementaciones empresariales, no se recomienda habilitar el modo de desarrollador, que usan ambos métodos.</span><span class="sxs-lookup"><span data-stu-id="2eafc-110">For enterprise deployments we do not recommend enabling Developer Mode, which both of these methods use.</span></span> <span data-ttu-id="2eafc-111">Si está interesado en un método de implementación de aplicaciones seguras, revise Nuestra administración [de aplicaciones: Información general.](app-deploy-overview.md)</span><span class="sxs-lookup"><span data-stu-id="2eafc-111">If you are interested in a secure app deployment method please review our [App Management: Overview](app-deploy-overview.md).</span></span>
>
> <span data-ttu-id="2eafc-112">Si busca cualquiera de los métodos de instalación de aplicaciones para desarrolladores HoloLens 2 dispositivos, consulte:</span><span class="sxs-lookup"><span data-stu-id="2eafc-112">If you are looking for either developer method of app installation for HoloLens 2 devices please refer to:</span></span>
> - [<span data-ttu-id="2eafc-113">Portal de dispositivos: Instalación de una aplicación</span><span class="sxs-lookup"><span data-stu-id="2eafc-113">Device Portal: Installing an App</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [<span data-ttu-id="2eafc-114">Uso Visual Studio para implementar y depurar aplicaciones</span><span class="sxs-lookup"><span data-stu-id="2eafc-114">Using Visual Studio to deploy and debug Apps</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <a name="install-custom-apps"></a><span data-ttu-id="2eafc-115">Instalación de aplicaciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="2eafc-115">Install custom apps</span></span>

<span data-ttu-id="2eafc-116">Puede instalar sus propias aplicaciones en HoloLens mediante el Portal de dispositivos o implementando las aplicaciones desde Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2eafc-116">You can install your own applications on HoloLens either by using the Device Portal or by deploying the apps from Visual Studio.</span></span>

### <a name="installing-an-application-package-with-the-device-portal"></a><span data-ttu-id="2eafc-117">Instalación de un paquete de aplicación con el Portal de dispositivos</span><span class="sxs-lookup"><span data-stu-id="2eafc-117">Installing an application package with the Device Portal</span></span>

1. <span data-ttu-id="2eafc-118">Establezca una conexión de [Portal de dispositivos](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) al holoLens de destino.</span><span class="sxs-lookup"><span data-stu-id="2eafc-118">Establish a connection from [Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) to the target HoloLens.</span></span>

1. <span data-ttu-id="2eafc-119">En el panel de navegación izquierdo, vaya a la **página** Aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="2eafc-119">In the left navigation, navigate to the **Apps** page.</span></span>

1. <span data-ttu-id="2eafc-120">En **Paquete de aplicación,** vaya al archivo .appx asociado a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2eafc-120">Under **App Package** browse to the .appx file that is associated with your application.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="2eafc-121">Asegúrese de hacer referencia a cualquier archivo de certificado y dependencia asociado.</span><span class="sxs-lookup"><span data-stu-id="2eafc-121">Make sure to reference any associated dependency and certificate files.</span></span>

1. <span data-ttu-id="2eafc-122">Seleccione **Ir**.</span><span class="sxs-lookup"><span data-stu-id="2eafc-122">Select **Go**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2eafc-123">![Instale el formulario de aplicación Portal de dispositivos Windows en Microsoft HoloLens](images/deviceportal-appmanager.jpg)</span><span class="sxs-lookup"><span data-stu-id="2eafc-123">![Install app form in Windows Device Portal on Microsoft HoloLens](images/deviceportal-appmanager.jpg)</span></span>

### <a name="deploying-from-microsoft-visual-studio-2015"></a><span data-ttu-id="2eafc-124">Implementación desde Microsoft Visual Studio 2015</span><span class="sxs-lookup"><span data-stu-id="2eafc-124">Deploying from Microsoft Visual Studio 2015</span></span>

1. <span data-ttu-id="2eafc-125">Abra la solución de Visual Studio aplicación (archivo .sln).</span><span class="sxs-lookup"><span data-stu-id="2eafc-125">Open your app's Visual Studio solution (.sln file).</span></span>

1. <span data-ttu-id="2eafc-126">Abra las propiedades del **proyecto.**</span><span class="sxs-lookup"><span data-stu-id="2eafc-126">Open the project's **Properties**.</span></span>

1. <span data-ttu-id="2eafc-127">Seleccione la siguiente configuración de compilación: **Master/x86/Remote Machine**.</span><span class="sxs-lookup"><span data-stu-id="2eafc-127">Select the following build configuration: **Master/x86/Remote Machine**.</span></span>

1. <span data-ttu-id="2eafc-128">Al seleccionar Equipo **remoto:**</span><span class="sxs-lookup"><span data-stu-id="2eafc-128">When you select **Remote Machine**:</span></span>
   - <span data-ttu-id="2eafc-129">Asegúrese de que la dirección apunta a la Wi-Fi IP de holoLens.</span><span class="sxs-lookup"><span data-stu-id="2eafc-129">Make sure the address points to the Wi-Fi IP address of your HoloLens.</span></span>
   - <span data-ttu-id="2eafc-130">Establezca la autenticación **en Universal (protocolo sin cifrar).**</span><span class="sxs-lookup"><span data-stu-id="2eafc-130">Set authentication to **Universal (Unencrypted Protocol)**.</span></span>
   
1. <span data-ttu-id="2eafc-131">Compile la solución.</span><span class="sxs-lookup"><span data-stu-id="2eafc-131">Build your solution.</span></span>

1. <span data-ttu-id="2eafc-132">Para implementar la aplicación desde el equipo de desarrollo en HoloLens, seleccione **Equipo remoto.**</span><span class="sxs-lookup"><span data-stu-id="2eafc-132">To deploy the app from your development PC to your HoloLens, select **Remote Machine**.</span></span> <span data-ttu-id="2eafc-133">Si ya tiene una compilación existente en HoloLens, seleccione **Sí** para instalar esta versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="2eafc-133">If you already have an existing build on the HoloLens, select **Yes** to install this newer version.</span></span>  

   ![Implementación remota de la máquina para que las aplicaciones Microsoft HoloLens en Visual Studio](images/vs2015-remotedeployment.jpg)  
   
1. <span data-ttu-id="2eafc-135">La aplicación se instalará e iniciará automáticamente en HoloLens.</span><span class="sxs-lookup"><span data-stu-id="2eafc-135">The application will install and auto launch on your HoloLens.</span></span>

<span data-ttu-id="2eafc-136">Después de instalar una aplicación, la encontrará en la lista Todas las **aplicaciones** **(Iniciar**  >  **todas las aplicaciones).**</span><span class="sxs-lookup"><span data-stu-id="2eafc-136">After you've installed an app, you'll find it in the **All apps** list (**Start** > **All apps**).</span></span>
