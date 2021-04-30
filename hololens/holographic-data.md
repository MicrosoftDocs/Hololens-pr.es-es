---
title: Buscar y guardar archivos en HoloLens
description: Obtenga información sobre cómo Explorador de archivos en HoloLens para abrir, ver y administrar archivos en el dispositivo de realidad mixta.
keywords: cómo, selector de archivos, archivos, fotos, vídeos, imágenes, OneDrive, almacenamiento, explorador de archivos, hololens
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
ms.openlocfilehash: 2d979b2cffd20589ddef7f11db5c7206eaea23cb
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2021
ms.locfileid: "108310084"
---
# <a name="find-open-and-save-files-on-hololens"></a><span data-ttu-id="3dffa-104">Buscar, abrir y guardar archivos en HoloLens</span><span class="sxs-lookup"><span data-stu-id="3dffa-104">Find, open, and save files on HoloLens</span></span>

<span data-ttu-id="3dffa-105">Los archivos que cree en HoloLens, incluidas las fotos y los vídeos, se guardan directamente en el dispositivo HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3dffa-105">Files you create on HoloLens, including photos and videos, are saved directly to your HoloLens device.</span></span> <span data-ttu-id="3dffa-106">Verlos y administrarlos de la misma manera que administraría los archivos en Windows 10:</span><span class="sxs-lookup"><span data-stu-id="3dffa-106">View and manage them in the same way you would manage files on Windows 10:</span></span>

- <span data-ttu-id="3dffa-107">Uso de la Explorador de archivos para acceder a carpetas locales.</span><span class="sxs-lookup"><span data-stu-id="3dffa-107">Using the File Explorer app to access local folders.</span></span>
- <span data-ttu-id="3dffa-108">Dentro del almacenamiento de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="3dffa-108">Within an app's storage.</span></span>
- <span data-ttu-id="3dffa-109">En una carpeta especial (como la biblioteca de vídeo o música).</span><span class="sxs-lookup"><span data-stu-id="3dffa-109">In a special folder (such as the video or music library).</span></span>
- <span data-ttu-id="3dffa-110">Uso de un servicio de almacenamiento que incluye una aplicación y un selector de archivos (como OneDrive).</span><span class="sxs-lookup"><span data-stu-id="3dffa-110">Using a storage service that includes an app and file picker (such as OneDrive).</span></span>
- <span data-ttu-id="3dffa-111">Uso de un equipo de escritorio conectado a HoloLens mediante un cable USB, mediante la compatibilidad con MTP (Protocolo de transferencia multimedia).</span><span class="sxs-lookup"><span data-stu-id="3dffa-111">Using a desktop PC connected to your HoloLens by using a USB cable, using MTP (Media Transfer Protocol) support.</span></span>

## <a name="view-files-on-hololens-using-file-explorer"></a><span data-ttu-id="3dffa-112">Visualización de archivos en HoloLens mediante Explorador de archivos</span><span class="sxs-lookup"><span data-stu-id="3dffa-112">View files on HoloLens using File Explorer</span></span>

> <span data-ttu-id="3dffa-113">Se aplica a todos HoloLens 2 dispositivos y HoloLens (1.ª generación) a partir de [Actualización de abril de 2018 de Windows 10 (RS4) para HoloLens](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018).</span><span class="sxs-lookup"><span data-stu-id="3dffa-113">Applies to all HoloLens 2 devices and HoloLens (1st gen) as of the [Windows 10 April 2018 Update (RS4) for HoloLens](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018).</span></span>

<span data-ttu-id="3dffa-114">Use Explorador de archivos en HoloLens para ver y administrar archivos en el dispositivo, incluidos objetos 3D, documentos e imágenes.</span><span class="sxs-lookup"><span data-stu-id="3dffa-114">Use File Explorer on HoloLens to view and manage files on your device, including 3D objects, documents, and pictures.</span></span> <span data-ttu-id="3dffa-115">Vaya a **Iniciar**   >  **todas las aplicaciones**   >  **Explorador de archivos** para empezar.</span><span class="sxs-lookup"><span data-stu-id="3dffa-115">Go to **Start**  > **All apps**  > **File Explorer** to get started.</span></span>

> [!TIP]
> <span data-ttu-id="3dffa-116">Si no aparece ningún archivo en Explorador de archivos, seleccione **Este dispositivo** en el panel superior izquierdo.</span><span class="sxs-lookup"><span data-stu-id="3dffa-116">If there are no files listed in File Explorer, select **This Device** in the top left pane.</span></span>

<span data-ttu-id="3dffa-117">Si no ve ningún archivo en Explorador de archivos, el filtro "Reciente" puede estar activo (el icono de reloj se resalta en el panel izquierdo).</span><span class="sxs-lookup"><span data-stu-id="3dffa-117">If you don’t see any files in File Explorer, the "Recent" filter may be active (clock icon is highlighted in left pane).</span></span> <span data-ttu-id="3dffa-118">Para corregirlo, seleccione **el** icono de documento Este dispositivo en el panel izquierdo (debajo del icono de reloj) o abra el menú y seleccione Este **dispositivo.**</span><span class="sxs-lookup"><span data-stu-id="3dffa-118">To fix this, select the **This Device** document icon in the left pane (beneath the clock icon), or open the menu and select **This Device**.</span></span>

## <a name="find-and-view-your-photos-and-videos"></a><span data-ttu-id="3dffa-119">Buscar y ver fotos y vídeos</span><span class="sxs-lookup"><span data-stu-id="3dffa-119">Find and view your photos and videos</span></span>

<span data-ttu-id="3dffa-120">[La captura de realidad mixta](holographic-photos-and-videos.md) le permite tomar fotos y vídeos de realidad mixta en HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3dffa-120">[Mixed reality capture](holographic-photos-and-videos.md) lets you take mixed reality photos and videos on HoloLens.</span></span>  <span data-ttu-id="3dffa-121">Estas fotos y vídeos se guardan en la carpeta Camera Roll del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3dffa-121">These photos and videos are saved to the device's Camera Roll folder.</span></span>

<span data-ttu-id="3dffa-122">Puede acceder a fotos y vídeos tomados con HoloLens mediante:</span><span class="sxs-lookup"><span data-stu-id="3dffa-122">You can access photos and videos taken with HoloLens by:</span></span>

- <span data-ttu-id="3dffa-123">acceder al roll de cámara directamente a través de [la aplicación Fotos](holographic-photos-and-videos.md).</span><span class="sxs-lookup"><span data-stu-id="3dffa-123">accessing the Camera Roll directly through the [Photos app](holographic-photos-and-videos.md).</span></span>
- <span data-ttu-id="3dffa-124">carga de fotos y vídeos en el almacenamiento en la nube mediante la sincronización de fotos y vídeos en OneDrive.</span><span class="sxs-lookup"><span data-stu-id="3dffa-124">uploading photos and videos to cloud storage by syncing your photos and videos to OneDrive.</span></span>
- <span data-ttu-id="3dffa-125">mediante la Captura de realidad mixta de la [Portal de dispositivos Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).</span><span class="sxs-lookup"><span data-stu-id="3dffa-125">using the Mixed Reality Capture page of the [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).</span></span>

### <a name="photos-app"></a><span data-ttu-id="3dffa-126">Aplicación Fotos</span><span class="sxs-lookup"><span data-stu-id="3dffa-126">Photos app</span></span>

<span data-ttu-id="3dffa-127">La aplicación Fotos es una de las aplicaciones predeterminadas del **menú** Inicio y viene integrada con HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3dffa-127">The Photos app is one of the default apps on the **Start** menu, and comes built-in with HoloLens.</span></span> <span data-ttu-id="3dffa-128">Obtenga más información sobre [el uso de la aplicación Fotos para ver el contenido.](holographic-photos-and-videos.md)</span><span class="sxs-lookup"><span data-stu-id="3dffa-128">Learn more about [using the Photos app to view content](holographic-photos-and-videos.md).</span></span>

<span data-ttu-id="3dffa-129">También puede instalar la aplicación [OneDrive desde](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) el Microsoft Store sincronizar fotos con otros dispositivos.</span><span class="sxs-lookup"><span data-stu-id="3dffa-129">You can also install the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store to sync photos to other devices.</span></span>

### <a name="onedrive-app"></a><span data-ttu-id="3dffa-130">Aplicación OneDrive</span><span class="sxs-lookup"><span data-stu-id="3dffa-130">OneDrive app</span></span>

<span data-ttu-id="3dffa-131">[OneDrive](https://onedrive.live.com/) le permite acceder, administrar y compartir sus fotos y vídeos con cualquier dispositivo y con cualquier usuario.</span><span class="sxs-lookup"><span data-stu-id="3dffa-131">[OneDrive](https://onedrive.live.com/) lets you access, manage, and share your photos and videos with any device and with any user.</span></span> <span data-ttu-id="3dffa-132">Para acceder a las fotos y vídeos capturados en HoloLens, descargue la aplicación [OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) desde la Microsoft Store en HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3dffa-132">To access the photos and videos captured on HoloLens, download the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store on your HoloLens.</span></span> <span data-ttu-id="3dffa-133">Una vez descargado, abra la aplicación OneDrive y seleccione **Settings** Camera upload  >  **(Configuración& cargar cámara)** y active **Camera upload (Cargar cámara).**</span><span class="sxs-lookup"><span data-stu-id="3dffa-133">Once downloaded, open the OneDrive app and select **Settings** > **Camera upload**, and turn on **Camera upload**.</span></span>

### <a name="connect-to-a-pc"></a><span data-ttu-id="3dffa-134">Conexión a un equipo</span><span class="sxs-lookup"><span data-stu-id="3dffa-134">Connect to a PC</span></span>

<span data-ttu-id="3dffa-135">Si HoloLens ejecuta la actualización de abril de [2018](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) de Windows 10 o posterior, puede conectar holoLens a un equipo Windows 10 mediante un cable USB para examinar fotos y vídeos en el dispositivo mediante MTP (protocolo de transferencia multimedia).</span><span class="sxs-lookup"><span data-stu-id="3dffa-135">If your HoloLens is running the [Windows 10 April 2018 update](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) or later, you can connect your HoloLens to a Windows 10 PC by using a USB cable to browse photos and videos on the device by using MTP (media transfer protocol).</span></span> <span data-ttu-id="3dffa-136">Deberá asegurarse de que el dispositivo está desbloqueado para examinar los archivos si tiene un PIN o una contraseña configurados en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3dffa-136">You'll need to make sure the device is unlocked to browse files if you have a PIN or password set up on your device.</span></span>  

<span data-ttu-id="3dffa-137">Si ha habilitado el [Portal de dispositivos Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal), puede usarlo para examinar, recuperar y administrar las fotos y vídeos almacenados en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3dffa-137">If you have enabled the [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal), you can use it to browse, retrieve, and manage the photos and videos stored on your device.</span></span>

## <a name="access-files-within-an-app"></a><span data-ttu-id="3dffa-138">Acceso a archivos dentro de una aplicación</span><span class="sxs-lookup"><span data-stu-id="3dffa-138">Access files within an app</span></span>

<span data-ttu-id="3dffa-139">Si una aplicación guarda archivos en el dispositivo, puede usar esa aplicación para acceder a ellos.</span><span class="sxs-lookup"><span data-stu-id="3dffa-139">If an application saves files on your device, you can use that application to access them.</span></span>

### <a name="requesting-files-from-another-app"></a><span data-ttu-id="3dffa-140">Solicitud de archivos desde otra aplicación</span><span class="sxs-lookup"><span data-stu-id="3dffa-140">Requesting files from another app</span></span>

<span data-ttu-id="3dffa-141">Una aplicación puede solicitar que guarde un archivo o abra un archivo desde otra aplicación mediante el uso de [selectores de archivos](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers).</span><span class="sxs-lookup"><span data-stu-id="3dffa-141">An application can request to save a file or open a file from another app by using [file pickers](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers).</span></span>

### <a name="known-folders"></a><span data-ttu-id="3dffa-142">Carpetas conocidas</span><span class="sxs-lookup"><span data-stu-id="3dffa-142">Known folders</span></span>

<span data-ttu-id="3dffa-143">HoloLens admite varias carpetas [conocidas](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) a las que las aplicaciones pueden solicitar permiso de acceso.</span><span class="sxs-lookup"><span data-stu-id="3dffa-143">HoloLens supports a number of [known folders](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) that apps can request permission to access.</span></span>

## <a name="view-hololens-files-on-your-pc"></a><span data-ttu-id="3dffa-144">Visualización de archivos de HoloLens en el equipo</span><span class="sxs-lookup"><span data-stu-id="3dffa-144">View HoloLens files on your PC</span></span>

<span data-ttu-id="3dffa-145">Al igual que otros dispositivos móviles, conecte HoloLens al equipo de escritorio mediante MTP (Protocolo de transferencia multimedia) y abra Explorador de archivos en el equipo para acceder a las bibliotecas de HoloLens para facilitar la transferencia.</span><span class="sxs-lookup"><span data-stu-id="3dffa-145">Similar to other mobile devices, connect HoloLens to your desktop PC using MTP (Media Transfer Protocol) and open File Explorer on the PC to access your HoloLens libraries for easy transfer.</span></span>

<span data-ttu-id="3dffa-146">Para ver los archivos de HoloLens Explorador de archivos en el equipo:</span><span class="sxs-lookup"><span data-stu-id="3dffa-146">To see your HoloLens files in File Explorer on your PC:</span></span>

1. <span data-ttu-id="3dffa-147">Inicie sesión en HoloLens y, a continuación, conéctelo al equipo mediante el cable USB que se incluye con HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3dffa-147">Sign in to HoloLens, then plug it into the PC using the USB cable that came with the HoloLens.</span></span>

1. <span data-ttu-id="3dffa-148">Seleccione **Abrir dispositivo para ver los** archivos Explorador de archivos o abra Explorador de archivos en el equipo y vaya al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3dffa-148">Select **Open Device to view files with File Explorer**, or open File Explorer on the PC and navigate to the device.</span></span>

<span data-ttu-id="3dffa-149">Para ver información sobre HoloLens, haga clic con el botón derecho en el nombre del dispositivo Explorador de archivos en el equipo y, a continuación, **seleccione Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="3dffa-149">To see info about your HoloLens, right-click the device name in File Explorer on your PC, then select **Properties**.</span></span>

> [!NOTE]
> <span data-ttu-id="3dffa-150">HoloLens (1.ª generación) no admite la conexión a unidades de disco duro externas o tarjetas SD.</span><span class="sxs-lookup"><span data-stu-id="3dffa-150">HoloLens (1st gen) does not support connecting to external hard drives or SD cards.</span></span>

## <a name="sync-to-the-cloud"></a><span data-ttu-id="3dffa-151">Sincronización con la nube</span><span class="sxs-lookup"><span data-stu-id="3dffa-151">Sync to the cloud</span></span>

<span data-ttu-id="3dffa-152">Para sincronizar fotos y otros archivos desde HoloLens a la nube, instale y configure OneDrive en HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3dffa-152">To sync photos and other files from your HoloLens to the cloud, install and set up OneDrive on HoloLens.</span></span> <span data-ttu-id="3dffa-153">Para obtener OneDrive, busque en la Microsoft Store en HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3dffa-153">To get OneDrive, search for it in the Microsoft Store on your HoloLens.</span></span>

<span data-ttu-id="3dffa-154">HoloLens no hace una copia de seguridad de los archivos y los datos de la aplicación, por lo que es una buena idea guardar lo importante en OneDrive.</span><span class="sxs-lookup"><span data-stu-id="3dffa-154">HoloLens doesn't back up app files and data, so it's a good idea to save your important stuff to OneDrive.</span></span> <span data-ttu-id="3dffa-155">De este modo, si restablece el dispositivo o desinstala una aplicación, se realizará una copia de seguridad de la información.</span><span class="sxs-lookup"><span data-stu-id="3dffa-155">That way, if you reset your device or uninstall an app, your info will be backed up.</span></span>
