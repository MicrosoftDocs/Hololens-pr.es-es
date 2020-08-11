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
# Buscar, abrir y guardar archivos en HoloLens

Los archivos que crees en HoloLens, incluidas las fotos y los vídeos, se guardan directamente en tu dispositivo HoloLens. Puedes verlos y administrarlos de la misma manera que lo harías en Windows 10:

- Usar la aplicación explorador de archivos para obtener acceso a las carpetas locales.
- Dentro del almacenamiento de una aplicación.
- En una carpeta especial (como la biblioteca de vídeos o música).
- Usar un servicio de almacenamiento que incluya un selector de aplicaciones y archivos (como OneDrive).
- Usar un equipo de escritorio conectado a tu HoloLens mediante un cable USB y con soporte técnico de MTP (Protocolo de transferencia multimedia).

## Ver archivos en HoloLens con el explorador de archivos

> Se aplica a todos los dispositivos HoloLens 2 y HoloLens (1 ª gen) a partir de la [actualización de 2018 (RS4) de Windows 10 de abril](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018).

Use el explorador de archivos en HoloLens para ver y administrar archivos en el dispositivo, incluidos objetos 3D, documentos e imágenes. Vaya a **iniciar**el   >  Explorador de archivos de**todas las aplicaciones**   >  **File Explorer** para comenzar.

> [!TIP]
> Si no hay ningún archivo en el explorador de archivos, **selecciónelo** en el panel superior izquierdo.

Si no ve ningún archivo en el explorador de archivos, es posible que el filtro "recientes" esté activo (el icono de reloj está resaltado en el panel izquierdo). Para corregir esto, seleccione el icono de documento de **este dispositivo** en el panel izquierdo (debajo del icono de reloj) o abra el menú y seleccione **este dispositivo**.

## Buscar y ver las fotos y los vídeos

La [captura de realidad mixta](holographic-photos-and-videos.md) te permite tomar fotos y vídeos de realidad mixta en HoloLens.  Estas fotos y vídeos se guardan en la carpeta álbum de cámara del dispositivo.

Puede obtener acceso a fotos y vídeos tomados con HoloLens de la siguiente manera:

- acceder a la cámara directamente a través de la [aplicación fotos](holographic-photos-and-videos.md).
- cargar fotos y vídeos en el almacenamiento en la nube sincronizando sus fotos y vídeos con OneDrive.
- usando la página de captura de realidad mixta de [Windows Device portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).

### Aplicación Fotos

La aplicación fotos es una de las aplicaciones predeterminadas en el menú **Inicio** y viene integrada con HoloLens. Obtenga más información sobre [el uso de la aplicación fotos para ver el contenido](holographic-photos-and-videos.md).

También puede instalar la [aplicación de OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) desde Microsoft Store para sincronizar fotos en otros dispositivos.

### Aplicación OneDrive

[OneDrive](https://onedrive.live.com/) le permite acceder a sus fotos y vídeos, administrarlos y compartirlos con cualquier dispositivo y con cualquier usuario. Para acceder a las fotos y los vídeos capturados en HoloLens, descargue la [aplicación de OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) desde Microsoft Store en hololens. Una vez descargado, abra la aplicación de OneDrive y seleccione **configuración**  >  **carga**de la cámara y Active **carga**de la cámara.

### Conectarse a un equipo PC

Si tu HoloLens ejecuta la [actualización de 2018 de abril de](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) o posterior, puedes conectar tu hololens a un equipo con Windows 10 con un cable USB para examinar las fotos y los vídeos en el dispositivo con MTP (Protocolo de transferencia multimedia). Tendrá que asegurarse de que el dispositivo está desbloqueado para examinar archivos si tiene un PIN o una contraseña configurados en su dispositivo.  

Si ha habilitado [Windows Device portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal), puede usarlo para examinar, recuperar y administrar las fotos y los vídeos almacenados en el dispositivo.

## Acceder a archivos dentro de una aplicación

Si una aplicación guarda archivos en el dispositivo, puede usar esa aplicación para acceder a ellos.

### Solicitar archivos de otra aplicación

Una aplicación puede solicitar guardar un archivo o abrir un archivo de otra aplicación con [selectores de archivos](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers).

### Carpetas conocidas

HoloLens es compatible con varias [carpetas conocidas a las que las](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) aplicaciones pueden solicitar permiso de acceso.

## Ver archivos de HoloLens en su equipo PC

Al igual que otros dispositivos móviles, conéctate a HoloLens a tu PC de escritorio con MTP (Protocolo de transferencia multimedia) y abre el explorador de archivos en el equipo para acceder a tus bibliotecas de HoloLens y facilitar la transferencia.

Para ver tus archivos de HoloLens en el explorador de archivos de tu equipo:

1. Inicia sesión en HoloLens y luego conéctelo en el equipo con el cable USB que venía con HoloLens.

1. Seleccione **abrir dispositivo para ver los archivos con el explorador**de archivos o abra el explorador de archivos en el equipo PC y vaya al dispositivo.

Para ver la información sobre HoloLens, haga clic con el botón derecho en el nombre del dispositivo en el explorador de archivos de su equipo y, a continuación, seleccione **propiedades**.

> [!NOTE]
> HoloLens (1. ª gen) no admite la conexión a unidades de disco duro externas ni a tarjetas SD.

## Sincronizar con la nube

Para sincronizar fotos y otros archivos desde HoloLens a la nube, instale y configure OneDrive en HoloLens. Para obtener OneDrive, búsquelo en la tienda de Microsoft en HoloLens.

HoloLens no realiza copias de seguridad de los archivos y los datos de la aplicación, por lo que es una buena idea guardar tus cosas importantes en OneDrive. De ese modo, si restableces el dispositivo o desinstala una aplicación, se hará una copia de seguridad de tu información.
