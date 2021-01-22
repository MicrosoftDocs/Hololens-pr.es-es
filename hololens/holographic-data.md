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
# Buscar, abrir y guardar archivos en HoloLens

Los archivos que creas en HoloLens, incluidas fotos y vídeos, se guardan directamente en tu dispositivo HoloLens. Ver y administrarlos de la misma manera que administraría los archivos en Windows 10:

- Usar la aplicación Explorador de archivos para obtener acceso a las carpetas locales.
- Dentro del almacenamiento de una aplicación.
- En una carpeta especial (como la biblioteca de vídeos o música).
- Usar un servicio de almacenamiento que incluya una aplicación y un selector de archivos (como OneDrive).
- Usar un equipo de escritorio conectado a HoloLens mediante un cable USB, mediante la compatibilidad con MTP (Protocolo de transferencia de medios).

## Ver archivos en HoloLens con el Explorador de archivos

> Se aplica a todos los dispositivos HoloLens 2 y HoloLens (1.ª generación) a partir de la actualización de [abril de 2018 de Windows 10 (RS4) para HoloLens](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018).

Usa el Explorador de archivos en HoloLens para ver y administrar archivos en el dispositivo, incluidos objetos 3D, documentos e imágenes. Ve a **Iniciar todas**las   >  **aplicaciones del**Explorador de   >  **archivos** para empezar.

> [!TIP]
> Si no hay archivos enumerados en el Explorador de archivos, selecciona **Este dispositivo** en el panel superior izquierdo.

Si no ve ningún archivo en el Explorador de archivos, el filtro "Reciente" puede estar activo (el icono de reloj se resalta en el panel izquierdo). Para solucionar este **** problema, seleccione el icono de documento Este dispositivo en el panel izquierdo (debajo del icono del reloj) o abra el menú y seleccione **Este dispositivo.**

## Buscar y ver fotos y vídeos

[La captura de realidad mixta](holographic-photos-and-videos.md) te permite tomar fotos y vídeos de realidad mixta en HoloLens.  Estas fotos y vídeos se guardan en la carpeta Dedo de cámara del dispositivo.

Puedes acceder a fotos y vídeos tomados con HoloLens mediante:

- obtener acceso al Roll de cámara directamente a [través de Fotos aplicación.](holographic-photos-and-videos.md)
- cargar fotos y vídeos en el almacenamiento en la nube sincronizando sus fotos y vídeos en OneDrive.
- con la página Captura de realidad mixta de [Windows Device Portal.](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture)

### Aplicación Fotos

La Fotos aplicación es una de las **** aplicaciones predeterminadas en el menú Inicio y viene integrada con HoloLens. Obtén más información [sobre cómo usar Fotos aplicación para ver contenido.](holographic-photos-and-videos.md)

También puede instalar la aplicación [de OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) desde Microsoft Store para sincronizar fotos con otros dispositivos.

### Aplicación OneDrive

[OneDrive](https://onedrive.live.com/) le permite acceder, administrar y compartir sus fotos y vídeos con cualquier dispositivo y con cualquier usuario. Para acceder a las fotos y los vídeos capturados en HoloLens, descargue la aplicación [de OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) desde Microsoft Store en su HoloLens. Una vez descargado, abra la aplicación de OneDrive y **seleccione**Cargar cámara de configuración y active la  >  **** carga de **cámara.**

### Conectarse a un equipo

Si HoloLens ejecuta la actualización de abril de [2018 de Windows 10](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) o posterior, puedes conectar holoLens a un equipo con Windows 10 mediante un cable USB para explorar fotos y vídeos en el dispositivo mediante MTP (protocolo de transferencia de medios). Deberás asegurarte de que el dispositivo esté desbloqueado para examinar archivos si tienes configurado un PIN o una contraseña en el dispositivo.  

Si has habilitado [Windows Device Portal,](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)puedes usarlo para examinar, recuperar y administrar las fotos y vídeos almacenados en el dispositivo.

## Acceder a archivos dentro de una aplicación

Si una aplicación guarda archivos en el dispositivo, puedes usar esa aplicación para acceder a ellos.

### Solicitar archivos desde otra aplicación

Una aplicación puede solicitar guardar un archivo o abrir un archivo desde otra aplicación mediante el uso de [selectores de archivos.](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers)

### Carpetas conocidas

HoloLens admite una serie de [carpetas conocidas a](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) las que las aplicaciones pueden solicitar permiso de acceso.

## Ver archivos holoLens en el equipo

Al igual que otros dispositivos móviles, conecta HoloLens a tu equipo de escritorio mediante MTP (Protocolo de transferencia de medios) y abre el Explorador de archivos en el equipo para acceder a las bibliotecas de HoloLens para facilitar la transferencia.

Para ver los archivos de HoloLens en el Explorador de archivos en el equipo:

1. Inicia sesión en HoloLens y, a continuación, enfózalo en el equipo con el cable USB que viene con HoloLens.

1. Selecciona **Abrir dispositivo para ver archivos con el Explorador de**archivos o abre el Explorador de archivos en el equipo y navega al dispositivo.

Para ver información sobre HoloLens, haz clic con el botón secundario en el nombre del dispositivo en el Explorador de archivos de tu equipo y, a continuación, selecciona **Propiedades.**

> [!NOTE]
> HoloLens (1.ª generación) no admite la conexión a unidades de disco duro externas o tarjetas SD.

## Sincronización con la nube

Para sincronizar fotos y otros archivos de HoloLens a la nube, instale y configure OneDrive en HoloLens. To get OneDrive, search for it in the Microsoft Store on your HoloLens.

HoloLens no hace una copia de seguridad de los datos y los archivos de la aplicación, por lo que es una buena idea guardar sus cosas importantes en OneDrive. De este modo, si restableces el dispositivo o desinstalas una aplicación, se realizará una copia de seguridad de la información.
