---
title: Buscar y guardar archivos en HoloLens
description: Aprenda a usar Explorador de archivos en HoloLens para abrir, ver y administrar archivos en el dispositivo de realidad mixta.
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
ms.openlocfilehash: 18dc962b869dafaea9ff9c605eef51fcbb35bfb2
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033182"
---
# <a name="find-open-and-save-files-on-hololens"></a>Búsqueda, apertura y almacenamiento de los archivos en HoloLens

Los archivos que crea en HoloLens, incluidas las fotos y los vídeos, se guardan directamente en el HoloLens dispositivo. Puede verlos y administrarlos de la misma manera que administraría los archivos en Windows 10:

- Usar la aplicación Explorador de archivos para acceder a las carpetas locales.
- Dentro del almacenamiento de una aplicación.
- En una carpeta especial (como la biblioteca de vídeo o música).
- Uso de un servicio de almacenamiento que incluye una aplicación y un selector de archivos (por ejemplo, OneDrive).
- El uso de un equipo de escritorio conectado a HoloLens mediante un cable USB, mediante la compatibilidad con MTP (Protocolo de transferencia multimedia).

## <a name="view-files-on-hololens-using-file-explorer"></a>Ver archivos en HoloLens mediante Explorador de archivos

> Se aplica a todos HoloLens 2 dispositivos y HoloLens (1ª generación) a partir de la actualización de Windows 10 de abril [de 2018 (RS4) para HoloLens](/windows/mixed-reality/release-notes-april-2018).

Use Explorador de archivos en HoloLens para ver y administrar archivos en el dispositivo, incluidos objetos 3D, documentos e imágenes. Vaya a **Iniciar todas** las   >  **aplicaciones**   >  **Explorador de archivos** para empezar.

> [!TIP]
> Si no hay ningún archivo en la lista Explorador de archivos, seleccione **Este dispositivo en** el panel superior izquierdo.

Si no ve ningún archivo en Explorador de archivos, el filtro "Reciente" puede estar activo (el icono de reloj se resalta en el panel izquierdo). Para solucionar este problema, seleccione el icono **de** documento Este dispositivo en el panel izquierdo (debajo del icono de reloj) o abra el menú y seleccione **Este dispositivo.**

## <a name="find-and-view-your-photos-and-videos"></a>Buscar y ver fotos y vídeos

[La captura de realidad mixta](holographic-photos-and-videos.md) le permite tomar fotos y vídeos de realidad mixta en HoloLens.  Estas fotos y vídeos se guardan en la carpeta Camera Roll del dispositivo.

Puede acceder a fotos y vídeos tomados con HoloLens:

- acceder al roll de cámara directamente a través [de Fotos aplicación](holographic-photos-and-videos.md).
- carga de fotos y vídeos en el almacenamiento en la nube mediante la sincronización de sus fotos y vídeos con OneDrive.
- mediante la Captura de realidad mixta de la [Windows Portal de dispositivos](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).

### <a name="photos-app"></a>Aplicación Fotos

La Fotos es una de las aplicaciones  predeterminadas en el menú Inicio y viene integrada con HoloLens. Obtenga más información sobre [el uso de la Fotos para ver el contenido.](holographic-photos-and-videos.md)

También puede instalar la aplicación [OneDrive desde](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) el Microsoft Store sincronizar fotos con otros dispositivos.

### <a name="onedrive-app"></a>OneDrive aplicación

[OneDrive](https://onedrive.live.com/) le permite acceder, administrar y compartir sus fotos y vídeos con cualquier dispositivo y con cualquier usuario. Para acceder a las fotos y vídeos capturados en HoloLens, descargue la aplicación [OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) desde la Microsoft Store en la HoloLens. Una vez descargado, abra la aplicación de OneDrive, seleccione **Configuración** Carga de cámara y  >  active La carga de la **cámara .**

### <a name="connect-to-a-pc"></a>Conectar a un equipo

Si el HoloLens ejecuta la actualización de abril de [2018](/windows/mixed-reality/release-notes-april-2018) de Windows 10 o posterior, puede conectar su HoloLens a un equipo Windows 10 mediante un cable USB para examinar fotos y vídeos en el dispositivo mediante MTP (protocolo de transferencia multimedia). Deberá asegurarse de que el dispositivo está desbloqueado para examinar los archivos si tiene un PIN o una contraseña configurados en el dispositivo.  

Si ha habilitado el [Windows Portal de dispositivos](/windows/mixed-reality/using-the-windows-device-portal), puede usarlo para examinar, recuperar y administrar las fotos y vídeos almacenados en el dispositivo.

## <a name="access-files-within-an-app"></a>Acceso a archivos dentro de una aplicación

Si una aplicación guarda archivos en el dispositivo, puede usar esa aplicación para acceder a ellos.

### <a name="requesting-files-from-another-app"></a>Solicitud de archivos desde otra aplicación

Una aplicación puede solicitar guardar un archivo o abrir un archivo desde otra aplicación mediante el uso de [selectores de archivos](/windows/mixed-reality/app-model#file-pickers).

### <a name="known-folders"></a>Carpetas conocidas

HoloLens admite una serie de [carpetas conocidas](/windows/mixed-reality/app-model#known-folders) a las que las aplicaciones pueden solicitar permiso de acceso.

## <a name="view-hololens-files-on-your-pc"></a>Ver HoloLens archivos en el equipo

De forma similar a otros dispositivos móviles, conecte HoloLens al equipo de escritorio mediante MTP (Protocolo de transferencia multimedia) y abra Explorador de archivos en el equipo para acceder a las bibliotecas de HoloLens para facilitar la transferencia.

Para ver los archivos HoloLens en Explorador de archivos en el equipo:

1. Inicie sesión en HoloLens y, a continuación, conéctelo al equipo mediante el cable USB que se incluye con el HoloLens.

1. Seleccione **Abrir dispositivo para ver los archivos Explorador de archivos** o abra Explorador de archivos en el equipo y vaya al dispositivo.

Para ver información sobre la HoloLens, haga clic con el botón derecho en el nombre del dispositivo en Explorador de archivos en el equipo y, a continuación, **seleccione Propiedades**.

> [!NOTE]
> HoloLens (1.ª generación) no admite la conexión a unidades de disco duro externas o tarjetas SD.

## <a name="sync-to-the-cloud"></a>Sincronización con la nube

Para sincronizar fotos y otros archivos de la HoloLens a la nube, instale y configure OneDrive en HoloLens. Para obtener OneDrive, busque en el Microsoft Store en el HoloLens.

HoloLens no hace una copia de seguridad de los datos y los archivos de la aplicación, por lo que es una buena idea guardar las cosas importantes en OneDrive. De este modo, si restablece el dispositivo o desinstala una aplicación, se hará una copia de seguridad de la información.
