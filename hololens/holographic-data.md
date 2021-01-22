---
title: Buscar y guardar archivos en HoloLens
description: Aprende a usar el Explorador de archivos en HoloLens para abrir, ver y administrar archivos en tu dispositivo de realidad mixta.
keywords: how-to, selector de archivos, archivos, fotos, vídeos, imágenes, OneDrive, almacenamiento, explorador de archivos, hololens
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
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283531"
---
# <span data-ttu-id="f77d2-104">Buscar, abrir y guardar archivos en HoloLens</span><span class="sxs-lookup"><span data-stu-id="f77d2-104">Find, open, and save files on HoloLens</span></span>

<span data-ttu-id="f77d2-105">Los archivos que creas en HoloLens, incluidas fotos y vídeos, se guardan directamente en tu dispositivo HoloLens.</span><span class="sxs-lookup"><span data-stu-id="f77d2-105">Files you create on HoloLens, including photos and videos, are saved directly to your HoloLens device.</span></span> <span data-ttu-id="f77d2-106">Ver y administrarlos de la misma manera que administraría los archivos en Windows 10:</span><span class="sxs-lookup"><span data-stu-id="f77d2-106">View and manage them in the same way you would manage files on Windows 10:</span></span>

- <span data-ttu-id="f77d2-107">Usar la aplicación Explorador de archivos para obtener acceso a las carpetas locales.</span><span class="sxs-lookup"><span data-stu-id="f77d2-107">Using the File Explorer app to access local folders.</span></span>
- <span data-ttu-id="f77d2-108">Dentro del almacenamiento de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="f77d2-108">Within an app's storage.</span></span>
- <span data-ttu-id="f77d2-109">En una carpeta especial (como la biblioteca de vídeos o música).</span><span class="sxs-lookup"><span data-stu-id="f77d2-109">In a special folder (such as the video or music library).</span></span>
- <span data-ttu-id="f77d2-110">Usar un servicio de almacenamiento que incluya una aplicación y un selector de archivos (como OneDrive).</span><span class="sxs-lookup"><span data-stu-id="f77d2-110">Using a storage service that includes an app and file picker (such as OneDrive).</span></span>
- <span data-ttu-id="f77d2-111">Usar un equipo de escritorio conectado a HoloLens mediante un cable USB, mediante la compatibilidad con MTP (Protocolo de transferencia de medios).</span><span class="sxs-lookup"><span data-stu-id="f77d2-111">Using a desktop PC connected to your HoloLens by using a USB cable, using MTP (Media Transfer Protocol) support.</span></span>

## <span data-ttu-id="f77d2-112">Ver archivos en HoloLens con el Explorador de archivos</span><span class="sxs-lookup"><span data-stu-id="f77d2-112">View files on HoloLens using File Explorer</span></span>

> <span data-ttu-id="f77d2-113">Se aplica a todos los dispositivos HoloLens 2 y HoloLens (1.ª generación) a partir de la actualización de [abril de 2018 de Windows 10 (RS4) para HoloLens](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018).</span><span class="sxs-lookup"><span data-stu-id="f77d2-113">Applies to all HoloLens 2 devices and HoloLens (1st gen) as of the [Windows 10 April 2018 Update (RS4) for HoloLens](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018).</span></span>

<span data-ttu-id="f77d2-114">Usa el Explorador de archivos en HoloLens para ver y administrar archivos en el dispositivo, incluidos objetos 3D, documentos e imágenes.</span><span class="sxs-lookup"><span data-stu-id="f77d2-114">Use File Explorer on HoloLens to view and manage files on your device, including 3D objects, documents, and pictures.</span></span> <span data-ttu-id="f77d2-115">Ve a **Iniciar todas**las   >  **aplicaciones del**Explorador de   >  **archivos** para empezar.</span><span class="sxs-lookup"><span data-stu-id="f77d2-115">Go to **Start**  > **All apps**  > **File Explorer** to get started.</span></span>

> [!TIP]
> <span data-ttu-id="f77d2-116">Si no hay archivos enumerados en el Explorador de archivos, selecciona **Este dispositivo** en el panel superior izquierdo.</span><span class="sxs-lookup"><span data-stu-id="f77d2-116">If there are no files listed in File Explorer, select **This Device** in the top left pane.</span></span>

<span data-ttu-id="f77d2-117">Si no ve ningún archivo en el Explorador de archivos, el filtro "Reciente" puede estar activo (el icono de reloj se resalta en el panel izquierdo).</span><span class="sxs-lookup"><span data-stu-id="f77d2-117">If you don’t see any files in File Explorer, the "Recent" filter may be active (clock icon is highlighted in left pane).</span></span> <span data-ttu-id="f77d2-118">Para solucionar este \*\*\*\* problema, seleccione el icono de documento Este dispositivo en el panel izquierdo (debajo del icono del reloj) o abra el menú y seleccione **Este dispositivo.**</span><span class="sxs-lookup"><span data-stu-id="f77d2-118">To fix this, select the **This Device** document icon in the left pane (beneath the clock icon), or open the menu and select **This Device**.</span></span>

## <span data-ttu-id="f77d2-119">Buscar y ver fotos y vídeos</span><span class="sxs-lookup"><span data-stu-id="f77d2-119">Find and view your photos and videos</span></span>

<span data-ttu-id="f77d2-120">[La captura de realidad mixta](holographic-photos-and-videos.md) te permite tomar fotos y vídeos de realidad mixta en HoloLens.</span><span class="sxs-lookup"><span data-stu-id="f77d2-120">[Mixed reality capture](holographic-photos-and-videos.md) lets you take mixed reality photos and videos on HoloLens.</span></span>  <span data-ttu-id="f77d2-121">Estas fotos y vídeos se guardan en la carpeta Dedo de cámara del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f77d2-121">These photos and videos are saved to the device's Camera Roll folder.</span></span>

<span data-ttu-id="f77d2-122">Puedes acceder a fotos y vídeos tomados con HoloLens mediante:</span><span class="sxs-lookup"><span data-stu-id="f77d2-122">You can access photos and videos taken with HoloLens by:</span></span>

- <span data-ttu-id="f77d2-123">obtener acceso al Roll de cámara directamente a [través de Fotos aplicación.](holographic-photos-and-videos.md)</span><span class="sxs-lookup"><span data-stu-id="f77d2-123">accessing the Camera Roll directly through the [Photos app](holographic-photos-and-videos.md).</span></span>
- <span data-ttu-id="f77d2-124">cargar fotos y vídeos en el almacenamiento en la nube sincronizando sus fotos y vídeos en OneDrive.</span><span class="sxs-lookup"><span data-stu-id="f77d2-124">uploading photos and videos to cloud storage by syncing your photos and videos to OneDrive.</span></span>
- <span data-ttu-id="f77d2-125">con la página Captura de realidad mixta de [Windows Device Portal.](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture)</span><span class="sxs-lookup"><span data-stu-id="f77d2-125">using the Mixed Reality Capture page of the [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).</span></span>

### <span data-ttu-id="f77d2-126">Aplicación Fotos</span><span class="sxs-lookup"><span data-stu-id="f77d2-126">Photos app</span></span>

<span data-ttu-id="f77d2-127">La Fotos aplicación es una de las \*\*\*\* aplicaciones predeterminadas en el menú Inicio y viene integrada con HoloLens.</span><span class="sxs-lookup"><span data-stu-id="f77d2-127">The Photos app is one of the default apps on the **Start** menu, and comes built-in with HoloLens.</span></span> <span data-ttu-id="f77d2-128">Obtén más información [sobre cómo usar Fotos aplicación para ver contenido.](holographic-photos-and-videos.md)</span><span class="sxs-lookup"><span data-stu-id="f77d2-128">Learn more about [using the Photos app to view content](holographic-photos-and-videos.md).</span></span>

<span data-ttu-id="f77d2-129">También puede instalar la aplicación [de OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) desde Microsoft Store para sincronizar fotos con otros dispositivos.</span><span class="sxs-lookup"><span data-stu-id="f77d2-129">You can also install the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store to sync photos to other devices.</span></span>

### <span data-ttu-id="f77d2-130">Aplicación OneDrive</span><span class="sxs-lookup"><span data-stu-id="f77d2-130">OneDrive app</span></span>

<span data-ttu-id="f77d2-131">[OneDrive](https://onedrive.live.com/) le permite acceder, administrar y compartir sus fotos y vídeos con cualquier dispositivo y con cualquier usuario.</span><span class="sxs-lookup"><span data-stu-id="f77d2-131">[OneDrive](https://onedrive.live.com/) lets you access, manage, and share your photos and videos with any device and with any user.</span></span> <span data-ttu-id="f77d2-132">Para acceder a las fotos y los vídeos capturados en HoloLens, descargue la aplicación [de OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) desde Microsoft Store en su HoloLens.</span><span class="sxs-lookup"><span data-stu-id="f77d2-132">To access the photos and videos captured on HoloLens, download the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store on your HoloLens.</span></span> <span data-ttu-id="f77d2-133">Una vez descargado, abra la aplicación de OneDrive y **seleccione**Cargar cámara de configuración y active la  >  \*\*\*\* carga de **cámara.**</span><span class="sxs-lookup"><span data-stu-id="f77d2-133">Once downloaded, open the OneDrive app and select **Settings** > **Camera upload**, and turn on **Camera upload**.</span></span>

### <span data-ttu-id="f77d2-134">Conectarse a un equipo</span><span class="sxs-lookup"><span data-stu-id="f77d2-134">Connect to a PC</span></span>

<span data-ttu-id="f77d2-135">Si HoloLens ejecuta la actualización de abril de [2018 de Windows 10](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) o posterior, puedes conectar holoLens a un equipo con Windows 10 mediante un cable USB para explorar fotos y vídeos en el dispositivo mediante MTP (protocolo de transferencia de medios).</span><span class="sxs-lookup"><span data-stu-id="f77d2-135">If your HoloLens is running the [Windows 10 April 2018 update](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) or later, you can connect your HoloLens to a Windows 10 PC by using a USB cable to browse photos and videos on the device by using MTP (media transfer protocol).</span></span> <span data-ttu-id="f77d2-136">Deberás asegurarte de que el dispositivo esté desbloqueado para examinar archivos si tienes configurado un PIN o una contraseña en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f77d2-136">You'll need to make sure the device is unlocked to browse files if you have a PIN or password set up on your device.</span></span>  

<span data-ttu-id="f77d2-137">Si has habilitado [Windows Device Portal,](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)puedes usarlo para examinar, recuperar y administrar las fotos y vídeos almacenados en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f77d2-137">If you have enabled the [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal), you can use it to browse, retrieve, and manage the photos and videos stored on your device.</span></span>

## <span data-ttu-id="f77d2-138">Acceder a archivos dentro de una aplicación</span><span class="sxs-lookup"><span data-stu-id="f77d2-138">Access files within an app</span></span>

<span data-ttu-id="f77d2-139">Si una aplicación guarda archivos en el dispositivo, puedes usar esa aplicación para acceder a ellos.</span><span class="sxs-lookup"><span data-stu-id="f77d2-139">If an application saves files on your device, you can use that application to access them.</span></span>

### <span data-ttu-id="f77d2-140">Solicitar archivos desde otra aplicación</span><span class="sxs-lookup"><span data-stu-id="f77d2-140">Requesting files from another app</span></span>

<span data-ttu-id="f77d2-141">Una aplicación puede solicitar guardar un archivo o abrir un archivo desde otra aplicación mediante el uso de [selectores de archivos.](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers)</span><span class="sxs-lookup"><span data-stu-id="f77d2-141">An application can request to save a file or open a file from another app by using [file pickers](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers).</span></span>

### <span data-ttu-id="f77d2-142">Carpetas conocidas</span><span class="sxs-lookup"><span data-stu-id="f77d2-142">Known folders</span></span>

<span data-ttu-id="f77d2-143">HoloLens admite una serie de [carpetas conocidas a](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) las que las aplicaciones pueden solicitar permiso de acceso.</span><span class="sxs-lookup"><span data-stu-id="f77d2-143">HoloLens supports a number of [known folders](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) that apps can request permission to access.</span></span>

## <span data-ttu-id="f77d2-144">Ver archivos holoLens en el equipo</span><span class="sxs-lookup"><span data-stu-id="f77d2-144">View HoloLens files on your PC</span></span>

<span data-ttu-id="f77d2-145">Al igual que otros dispositivos móviles, conecta HoloLens a tu equipo de escritorio mediante MTP (Protocolo de transferencia de medios) y abre el Explorador de archivos en el equipo para acceder a las bibliotecas de HoloLens para facilitar la transferencia.</span><span class="sxs-lookup"><span data-stu-id="f77d2-145">Similar to other mobile devices, connect HoloLens to your desktop PC using MTP (Media Transfer Protocol) and open File Explorer on the PC to access your HoloLens libraries for easy transfer.</span></span>

<span data-ttu-id="f77d2-146">Para ver los archivos de HoloLens en el Explorador de archivos en el equipo:</span><span class="sxs-lookup"><span data-stu-id="f77d2-146">To see your HoloLens files in File Explorer on your PC:</span></span>

1. <span data-ttu-id="f77d2-147">Inicia sesión en HoloLens y, a continuación, enfózalo en el equipo con el cable USB que viene con HoloLens.</span><span class="sxs-lookup"><span data-stu-id="f77d2-147">Sign in to HoloLens, then plug it into the PC using the USB cable that came with the HoloLens.</span></span>

1. <span data-ttu-id="f77d2-148">Selecciona **Abrir dispositivo para ver archivos con el Explorador de**archivos o abre el Explorador de archivos en el equipo y navega al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f77d2-148">Select **Open Device to view files with File Explorer**, or open File Explorer on the PC and navigate to the device.</span></span>

<span data-ttu-id="f77d2-149">Para ver información sobre HoloLens, haz clic con el botón secundario en el nombre del dispositivo en el Explorador de archivos de tu equipo y, a continuación, selecciona **Propiedades.**</span><span class="sxs-lookup"><span data-stu-id="f77d2-149">To see info about your HoloLens, right-click the device name in File Explorer on your PC, then select **Properties**.</span></span>

> [!NOTE]
> <span data-ttu-id="f77d2-150">HoloLens (1.ª generación) no admite la conexión a unidades de disco duro externas o tarjetas SD.</span><span class="sxs-lookup"><span data-stu-id="f77d2-150">HoloLens (1st gen) does not support connecting to external hard drives or SD cards.</span></span>

## <span data-ttu-id="f77d2-151">Sincronización con la nube</span><span class="sxs-lookup"><span data-stu-id="f77d2-151">Sync to the cloud</span></span>

<span data-ttu-id="f77d2-152">Para sincronizar fotos y otros archivos de HoloLens a la nube, instale y configure OneDrive en HoloLens.</span><span class="sxs-lookup"><span data-stu-id="f77d2-152">To sync photos and other files from your HoloLens to the cloud, install and set up OneDrive on HoloLens.</span></span> <span data-ttu-id="f77d2-153">To get OneDrive, search for it in the Microsoft Store on your HoloLens.</span><span class="sxs-lookup"><span data-stu-id="f77d2-153">To get OneDrive, search for it in the Microsoft Store on your HoloLens.</span></span>

<span data-ttu-id="f77d2-154">HoloLens no hace una copia de seguridad de los datos y los archivos de la aplicación, por lo que es una buena idea guardar sus cosas importantes en OneDrive.</span><span class="sxs-lookup"><span data-stu-id="f77d2-154">HoloLens doesn't back up app files and data, so it's a good idea to save your important stuff to OneDrive.</span></span> <span data-ttu-id="f77d2-155">De este modo, si restableces el dispositivo o desinstalas una aplicación, se realizará una copia de seguridad de la información.</span><span class="sxs-lookup"><span data-stu-id="f77d2-155">That way, if you reset your device or uninstall an app, your info will be backed up.</span></span>
