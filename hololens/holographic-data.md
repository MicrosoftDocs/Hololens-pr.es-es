---
title: Buscar y guardar archivos en HoloLens
description: Usar el explorador de archivos en HoloLens para ver y administrar archivos en el dispositivo
keywords: procedimientos, selector de archivos, archivos, fotos, vídeos, imágenes, OneDrive, almacenamiento, explorador de archivos, hololens
ms.assetid: 77d2e357-f65f-43c8-b62f-6cd9bf37070a
author: mattzmsft
ms.author: mazeller
manager: v-miegge
ms.reviewer: jarrettrenshaw
ms.date: 12/30/2019
ms.prod: hololens
ms.sitesec: library
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: fb3287f0a074eddeac0c7ee2871e289b93eafcac
ms.sourcegitcommit: 8b56f4b9b5f9c928fc361f18efcbea729055a0b2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/10/2020
ms.locfileid: "10919131"
---
# <span data-ttu-id="4044d-104">Buscar, abrir y guardar archivos en HoloLens</span><span class="sxs-lookup"><span data-stu-id="4044d-104">Find, open, and save files on HoloLens</span></span>

<span data-ttu-id="4044d-105">Los archivos que crees en HoloLens, incluidas las fotos y los vídeos, se guardan directamente en tu dispositivo HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4044d-105">Files you create on HoloLens, including photos and videos, are saved directly to your HoloLens device.</span></span> <span data-ttu-id="4044d-106">Puedes verlos y administrarlos de la misma manera que lo harías en Windows 10:</span><span class="sxs-lookup"><span data-stu-id="4044d-106">View and manage them in the same way you would manage files on Windows 10:</span></span>

- <span data-ttu-id="4044d-107">Usar la aplicación explorador de archivos para obtener acceso a las carpetas locales.</span><span class="sxs-lookup"><span data-stu-id="4044d-107">Using the File Explorer app to access local folders.</span></span>
- <span data-ttu-id="4044d-108">Dentro del almacenamiento de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="4044d-108">Within an app's storage.</span></span>
- <span data-ttu-id="4044d-109">En una carpeta especial (como la biblioteca de vídeos o música).</span><span class="sxs-lookup"><span data-stu-id="4044d-109">In a special folder (such as the video or music library).</span></span>
- <span data-ttu-id="4044d-110">Usar un servicio de almacenamiento que incluya un selector de aplicaciones y archivos (como OneDrive).</span><span class="sxs-lookup"><span data-stu-id="4044d-110">Using a storage service that includes an app and file picker (such as OneDrive).</span></span>
- <span data-ttu-id="4044d-111">Usar un equipo de escritorio conectado a tu HoloLens mediante un cable USB y con soporte técnico de MTP (Protocolo de transferencia multimedia).</span><span class="sxs-lookup"><span data-stu-id="4044d-111">Using a desktop PC connected to your HoloLens by using a USB cable, using MTP (Media Transfer Protocol) support.</span></span>

## <span data-ttu-id="4044d-112">Ver archivos en HoloLens con el explorador de archivos</span><span class="sxs-lookup"><span data-stu-id="4044d-112">View files on HoloLens using File Explorer</span></span>

> <span data-ttu-id="4044d-113">Se aplica a todos los dispositivos HoloLens 2 y HoloLens (1 ª gen) a partir de la [actualización de 2018 (RS4) de Windows 10 de abril](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018).</span><span class="sxs-lookup"><span data-stu-id="4044d-113">Applies to all HoloLens 2 devices and HoloLens (1st gen) as of the [Windows 10 April 2018 Update (RS4) for HoloLens](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018).</span></span>

<span data-ttu-id="4044d-114">Use el explorador de archivos en HoloLens para ver y administrar archivos en el dispositivo, incluidos objetos 3D, documentos e imágenes.</span><span class="sxs-lookup"><span data-stu-id="4044d-114">Use File Explorer on HoloLens to view and manage files on your device, including 3D objects, documents, and pictures.</span></span> <span data-ttu-id="4044d-115">Vaya a **iniciar**el   >  Explorador de archivos de**todas las aplicaciones**   >  **File Explorer** para comenzar.</span><span class="sxs-lookup"><span data-stu-id="4044d-115">Go to **Start**  > **All apps**  > **File Explorer** to get started.</span></span>

> [!TIP]
> <span data-ttu-id="4044d-116">Si no hay ningún archivo en el explorador de archivos, **selecciónelo** en el panel superior izquierdo.</span><span class="sxs-lookup"><span data-stu-id="4044d-116">If there are no files listed in File Explorer, select **This Device** in the top left pane.</span></span>

<span data-ttu-id="4044d-117">Si no ve ningún archivo en el explorador de archivos, es posible que el filtro "recientes" esté activo (el icono de reloj está resaltado en el panel izquierdo).</span><span class="sxs-lookup"><span data-stu-id="4044d-117">If you don’t see any files in File Explorer, the "Recent" filter may be active (clock icon is highlighted in left pane).</span></span> <span data-ttu-id="4044d-118">Para corregir esto, seleccione el icono de documento de **este dispositivo** en el panel izquierdo (debajo del icono de reloj) o abra el menú y seleccione **este dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="4044d-118">To fix this, select the **This Device** document icon in the left pane (beneath the clock icon), or open the menu and select **This Device**.</span></span>

## <span data-ttu-id="4044d-119">Buscar y ver las fotos y los vídeos</span><span class="sxs-lookup"><span data-stu-id="4044d-119">Find and view your photos and videos</span></span>

<span data-ttu-id="4044d-120">La [captura de realidad mixta](holographic-photos-and-videos.md) te permite tomar fotos y vídeos de realidad mixta en HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4044d-120">[Mixed reality capture](holographic-photos-and-videos.md) lets you take mixed reality photos and videos on HoloLens.</span></span>  <span data-ttu-id="4044d-121">Estas fotos y vídeos se guardan en la carpeta álbum de cámara del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4044d-121">These photos and videos are saved to the device's Camera Roll folder.</span></span>

<span data-ttu-id="4044d-122">Puede obtener acceso a fotos y vídeos tomados con HoloLens de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="4044d-122">You can access photos and videos taken with HoloLens by:</span></span>

- <span data-ttu-id="4044d-123">acceder a la cámara directamente a través de la [aplicación fotos](holographic-photos-and-videos.md).</span><span class="sxs-lookup"><span data-stu-id="4044d-123">accessing the Camera Roll directly through the [Photos app](holographic-photos-and-videos.md).</span></span>
- <span data-ttu-id="4044d-124">cargar fotos y vídeos en el almacenamiento en la nube sincronizando sus fotos y vídeos con OneDrive.</span><span class="sxs-lookup"><span data-stu-id="4044d-124">uploading photos and videos to cloud storage by syncing your photos and videos to OneDrive.</span></span>
- <span data-ttu-id="4044d-125">usando la página de captura de realidad mixta de [Windows Device portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).</span><span class="sxs-lookup"><span data-stu-id="4044d-125">using the Mixed Reality Capture page of the [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).</span></span>

### <span data-ttu-id="4044d-126">Aplicación Fotos</span><span class="sxs-lookup"><span data-stu-id="4044d-126">Photos app</span></span>

<span data-ttu-id="4044d-127">La aplicación fotos es una de las aplicaciones predeterminadas en el menú **Inicio** y viene integrada con HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4044d-127">The Photos app is one of the default apps on the **Start** menu, and comes built-in with HoloLens.</span></span> <span data-ttu-id="4044d-128">Obtenga más información sobre [el uso de la aplicación fotos para ver el contenido](holographic-photos-and-videos.md).</span><span class="sxs-lookup"><span data-stu-id="4044d-128">Learn more about [using the Photos app to view content](holographic-photos-and-videos.md).</span></span>

<span data-ttu-id="4044d-129">También puede instalar la [aplicación de OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) desde Microsoft Store para sincronizar fotos en otros dispositivos.</span><span class="sxs-lookup"><span data-stu-id="4044d-129">You can also install the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store to sync photos to other devices.</span></span>

### <span data-ttu-id="4044d-130">Aplicación OneDrive</span><span class="sxs-lookup"><span data-stu-id="4044d-130">OneDrive app</span></span>

<span data-ttu-id="4044d-131">[OneDrive](https://onedrive.live.com/) le permite acceder a sus fotos y vídeos, administrarlos y compartirlos con cualquier dispositivo y con cualquier usuario.</span><span class="sxs-lookup"><span data-stu-id="4044d-131">[OneDrive](https://onedrive.live.com/) lets you access, manage, and share your photos and videos with any device and with any user.</span></span> <span data-ttu-id="4044d-132">Para acceder a las fotos y los vídeos capturados en HoloLens, descargue la [aplicación de OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) desde Microsoft Store en hololens.</span><span class="sxs-lookup"><span data-stu-id="4044d-132">To access the photos and videos captured on HoloLens, download the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store on your HoloLens.</span></span> <span data-ttu-id="4044d-133">Una vez descargado, abra la aplicación de OneDrive y seleccione **configuración**  >  **carga**de la cámara y Active **carga**de la cámara.</span><span class="sxs-lookup"><span data-stu-id="4044d-133">Once downloaded, open the OneDrive app and select **Settings** > **Camera upload**, and turn on **Camera upload**.</span></span>

### <span data-ttu-id="4044d-134">Conectarse a un equipo PC</span><span class="sxs-lookup"><span data-stu-id="4044d-134">Connect to a PC</span></span>

<span data-ttu-id="4044d-135">Si tu HoloLens ejecuta la [actualización de 2018 de abril de](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) o posterior, puedes conectar tu hololens a un equipo con Windows 10 con un cable USB para examinar las fotos y los vídeos en el dispositivo con MTP (Protocolo de transferencia multimedia).</span><span class="sxs-lookup"><span data-stu-id="4044d-135">If your HoloLens is running the [Windows 10 April 2018 update](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) or later, you can connect your HoloLens to a Windows 10 PC by using a USB cable to browse photos and videos on the device by using MTP (media transfer protocol).</span></span> <span data-ttu-id="4044d-136">Tendrá que asegurarse de que el dispositivo está desbloqueado para examinar archivos si tiene un PIN o una contraseña configurados en su dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4044d-136">You'll need to make sure the device is unlocked to browse files if you have a PIN or password set up on your device.</span></span>  

<span data-ttu-id="4044d-137">Si ha habilitado [Windows Device portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal), puede usarlo para examinar, recuperar y administrar las fotos y los vídeos almacenados en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4044d-137">If you have enabled the [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal), you can use it to browse, retrieve, and manage the photos and videos stored on your device.</span></span>

## <span data-ttu-id="4044d-138">Acceder a archivos dentro de una aplicación</span><span class="sxs-lookup"><span data-stu-id="4044d-138">Access files within an app</span></span>

<span data-ttu-id="4044d-139">Si una aplicación guarda archivos en el dispositivo, puede usar esa aplicación para acceder a ellos.</span><span class="sxs-lookup"><span data-stu-id="4044d-139">If an application saves files on your device, you can use that application to access them.</span></span>

### <span data-ttu-id="4044d-140">Solicitar archivos de otra aplicación</span><span class="sxs-lookup"><span data-stu-id="4044d-140">Requesting files from another app</span></span>

<span data-ttu-id="4044d-141">Una aplicación puede solicitar guardar un archivo o abrir un archivo de otra aplicación con [selectores de archivos](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers).</span><span class="sxs-lookup"><span data-stu-id="4044d-141">An application can request to save a file or open a file from another app by using [file pickers](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers).</span></span>

### <span data-ttu-id="4044d-142">Carpetas conocidas</span><span class="sxs-lookup"><span data-stu-id="4044d-142">Known folders</span></span>

<span data-ttu-id="4044d-143">HoloLens es compatible con varias [carpetas conocidas a las que las](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) aplicaciones pueden solicitar permiso de acceso.</span><span class="sxs-lookup"><span data-stu-id="4044d-143">HoloLens supports a number of [known folders](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) that apps can request permission to access.</span></span>

## <span data-ttu-id="4044d-144">Ver archivos de HoloLens en su equipo PC</span><span class="sxs-lookup"><span data-stu-id="4044d-144">View HoloLens files on your PC</span></span>

<span data-ttu-id="4044d-145">Al igual que otros dispositivos móviles, conéctate a HoloLens a tu PC de escritorio con MTP (Protocolo de transferencia multimedia) y abre el explorador de archivos en el equipo para acceder a tus bibliotecas de HoloLens y facilitar la transferencia.</span><span class="sxs-lookup"><span data-stu-id="4044d-145">Similar to other mobile devices, connect HoloLens to your desktop PC using MTP (Media Transfer Protocol) and open File Explorer on the PC to access your HoloLens libraries for easy transfer.</span></span>

<span data-ttu-id="4044d-146">Para ver tus archivos de HoloLens en el explorador de archivos de tu equipo:</span><span class="sxs-lookup"><span data-stu-id="4044d-146">To see your HoloLens files in File Explorer on your PC:</span></span>

1. <span data-ttu-id="4044d-147">Inicia sesión en HoloLens y luego conéctelo en el equipo con el cable USB que venía con HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4044d-147">Sign in to HoloLens, then plug it into the PC using the USB cable that came with the HoloLens.</span></span>

1. <span data-ttu-id="4044d-148">Seleccione **abrir dispositivo para ver los archivos con el explorador**de archivos o abra el explorador de archivos en el equipo PC y vaya al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4044d-148">Select **Open Device to view files with File Explorer**, or open File Explorer on the PC and navigate to the device.</span></span>

<span data-ttu-id="4044d-149">Para ver la información sobre HoloLens, haga clic con el botón derecho en el nombre del dispositivo en el explorador de archivos de su equipo y, a continuación, seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="4044d-149">To see info about your HoloLens, right-click the device name in File Explorer on your PC, then select **Properties**.</span></span>

> [!NOTE]
> <span data-ttu-id="4044d-150">HoloLens (1. ª gen) no admite la conexión a unidades de disco duro externas ni a tarjetas SD.</span><span class="sxs-lookup"><span data-stu-id="4044d-150">HoloLens (1st gen) does not support connecting to external hard drives or SD cards.</span></span>

## <span data-ttu-id="4044d-151">Sincronizar con la nube</span><span class="sxs-lookup"><span data-stu-id="4044d-151">Sync to the cloud</span></span>

<span data-ttu-id="4044d-152">Para sincronizar fotos y otros archivos desde HoloLens a la nube, instale y configure OneDrive en HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4044d-152">To sync photos and other files from your HoloLens to the cloud, install and set up OneDrive on HoloLens.</span></span> <span data-ttu-id="4044d-153">Para obtener OneDrive, búsquelo en la tienda de Microsoft en HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4044d-153">To get OneDrive, search for it in the Microsoft Store on your HoloLens.</span></span>

<span data-ttu-id="4044d-154">HoloLens no realiza copias de seguridad de los archivos y los datos de la aplicación, por lo que es una buena idea guardar tus cosas importantes en OneDrive.</span><span class="sxs-lookup"><span data-stu-id="4044d-154">HoloLens doesn't back up app files and data, so it's a good idea to save your important stuff to OneDrive.</span></span> <span data-ttu-id="4044d-155">De ese modo, si restableces el dispositivo o desinstala una aplicación, se hará una copia de seguridad de tu información.</span><span class="sxs-lookup"><span data-stu-id="4044d-155">That way, if you reset your device or uninstall an app, your info will be backed up.</span></span>
