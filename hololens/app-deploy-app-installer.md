---
title: Cómo cargar y instalar aplicaciones a través del instalador de aplicaciones de HoloLens 2
description: Descargar diapositivas e instalar aplicaciones a través de la interfaz de usuario
keywords: App Management, App, hololens, instalador de aplicaciones
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 9/17/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 2387c0eb65efc312db4eea7118f3cca44ce6d4b6
ms.sourcegitcommit: 4ad9b6c73913808175b1a448d2be9e33592f65af
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2020
ms.locfileid: "11027490"
---
# <span data-ttu-id="ccf43-104">Instalar aplicaciones en HoloLens 2 a través del instalador de la aplicación</span><span class="sxs-lookup"><span data-stu-id="ccf43-104">Install Apps on HoloLens 2 via App Installer</span></span>

<span data-ttu-id="ccf43-105">Ahora los usuarios pueden instalar aplicaciones a través de paquetes de appx, sin necesidad de habilitar el modo de desarrollador ni usar Device portal.</span><span class="sxs-lookup"><span data-stu-id="ccf43-105">Users can now install Apps via Appx Bundles now without the need to enable Developer Mode or use Device Portal.</span></span> <span data-ttu-id="ccf43-106">Esta experiencia es sencilla para instalar aplicaciones en dispositivos locales o para compartir una aplicación con otra persona que no está familiarizada con otros métodos de instalación de aplicaciones en HoloLens.</span><span class="sxs-lookup"><span data-stu-id="ccf43-106">This experience is simple for installing Apps on local devices or sharing an app with someone else who is unfamiliar with other app install methods on HoloLens.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="ccf43-107">Actualmente, esta característica solo avalible en Windows Insider compila 19041.1377 +.</span><span class="sxs-lookup"><span data-stu-id="ccf43-107">This feature is currently only avalible in Windows Insider builds 19041.1377+.</span></span> <span data-ttu-id="ccf43-108">[Obtenga más información sobre cómo inscribirse en compilaciones de Windows Insider](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="ccf43-108">[Learn more on how to enroll in Windows Insider builds](hololens-insider.md).</span></span>

> [!NOTE]
> <span data-ttu-id="ccf43-109">La configuración de la solución de la aplicación debe ser **Master** o **Release** , ya que el instalador de la aplicación usará las dependencias de la tienda.</span><span class="sxs-lookup"><span data-stu-id="ccf43-109">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="ccf43-110">Más información sobre cómo [crear paquetes de aplicaciones](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span><span class="sxs-lookup"><span data-stu-id="ccf43-110">See more about [creating app packages](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

1.  <span data-ttu-id="ccf43-111">Asegúrate de que tu dispositivo HoloLens 2 esté encendido y de que hayas iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="ccf43-111">Ensure that your HoloLens 2 device is powered on and you are signed in.</span></span>
1.  <span data-ttu-id="ccf43-112">En su equipo, navegue hasta la aplicación personalizada y copie SUAPLICACIÓN. appxbundle a yourdevicename\Internal Storage\Downloads.</span><span class="sxs-lookup"><span data-stu-id="ccf43-112">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span> 
    <span data-ttu-id="ccf43-113">Una vez que haya terminado de copiar el archivo, puede desconectar el dispositivo y finalizar la instalación más tarde.</span><span class="sxs-lookup"><span data-stu-id="ccf43-113">After your finish copying your file you may disconnect your device and finish the install later.</span></span>
1.  <span data-ttu-id="ccf43-114">Desde tu dispositivo HoloLens 2 abre el **menú Inicio**, selecciona **todas las aplicaciones** e inicia la aplicación **Explorador de archivos** .</span><span class="sxs-lookup"><span data-stu-id="ccf43-114">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1.  <span data-ttu-id="ccf43-115">Vaya a la carpeta descargas.</span><span class="sxs-lookup"><span data-stu-id="ccf43-115">Navigate to the Downloads folder.</span></span> <span data-ttu-id="ccf43-116">Es posible que tenga que estar en el panel izquierdo de la aplicación, seleccione **este dispositivo** en primer lugar y, a continuación, vaya a descargas.</span><span class="sxs-lookup"><span data-stu-id="ccf43-116">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1.  <span data-ttu-id="ccf43-117">Seleccione el archivo SUAPLICACIÓN. appxbundle.</span><span class="sxs-lookup"><span data-stu-id="ccf43-117">Select the yourapp.appxbundle file.</span></span> 
1.  <span data-ttu-id="ccf43-118">Se iniciará el instalador de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ccf43-118">The App Installer will launch.</span></span> <span data-ttu-id="ccf43-119">Seleccione el botón **instalar** para instalar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ccf43-119">Select the **Install** button to install your app.</span></span> 

<span data-ttu-id="ccf43-120">La aplicación instalada se iniciará automáticamente al finalizar la instalación.</span><span class="sxs-lookup"><span data-stu-id="ccf43-120">The installed app will automatically launch upon the completion of installing.</span></span> 

![Instalación de MRTK ejemplos mediante el instalador de aplicaciones](images/hololens-app-installer-picture.jpg)

<span data-ttu-id="ccf43-122">Si la aplicación no se instaló correctamente, compruebe lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ccf43-122">If your app failed to install check the following:</span></span>
-   <span data-ttu-id="ccf43-123">Tu aplicación es una compilación de lanzamiento o maestra.</span><span class="sxs-lookup"><span data-stu-id="ccf43-123">Your app is either a Master or Release build.</span></span>
-   <span data-ttu-id="ccf43-124">Estás [conectado a Internet](hololens-network.md).</span><span class="sxs-lookup"><span data-stu-id="ccf43-124">You are [connected to the internet](hololens-network.md).</span></span>
-   <span data-ttu-id="ccf43-125">Los [puntos de conexión de Microsoft Store](hololens-offline.md) están correctamente configurados.</span><span class="sxs-lookup"><span data-stu-id="ccf43-125">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  
