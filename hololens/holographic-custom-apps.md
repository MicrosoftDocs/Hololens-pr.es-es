---
title: Administrar aplicaciones personalizadas para HoloLens
description: Carga de las aplicaciones personalizadas de la cara en HoloLens. Más información sobre la instalación y desinstalación de aplicaciones holográficas.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 07/01/2019
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
- HoloLens 2
ms.openlocfilehash: 12c5eedfab580be8acea48c1fc19b56c1ead08ac
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828865"
---
# Administrar aplicaciones personalizadas para HoloLens

HoloLens admite muchas aplicaciones existentes de Microsoft Store, así como nuevas aplicaciones creadas específicamente para HoloLens. Este artículo se centra en las aplicaciones holográficas personalizadas.  

Para obtener más información sobre las aplicaciones de la tienda, consulte [Administrar aplicaciones con la tienda](holographic-store-apps.md).

## Instalar aplicaciones personalizadas

Puedes instalar tus propias aplicaciones en HoloLens a través del portal de dispositivos o mediante la implementación de las aplicaciones desde Visual Studio.

### Instalar un paquete de aplicación con el portal de dispositivos

1. Establece una conexión de [portal de dispositivos](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) al HoloLens de destino.
1. En el navegación de la izquierda, vaya a la página **aplicaciones** .
1. En el paquete de la **aplicación** , busque el archivo. appx asociado a la aplicación.
   > [!IMPORTANT]
   > Asegúrese de hacer referencia a los archivos de dependencia y certificados asociados.

1. Seleccione **ir**.
   ![Instalar el formulario de aplicaciones en Windows Device portal en Microsoft HoloLens](images/deviceportal-appmanager.jpg)

### Implementar desde Microsoft Visual Studio 2015

1. Abra la solución de Visual Studio de la aplicación (archivo. sln).
1. Abra las **propiedades**del proyecto.
1. Seleccione la siguiente configuración de compilación: **principal/x86/máquina remota**.
1. Cuando seleccione **equipo remoto**:
   - Asegúrese de que la dirección apunta a la dirección IP de Wi-Fi de su HoloLens.
   - Configurar la autenticación a **universal (protocolo sin cifrar)**.
1. Cree su solución.
1. Para implementar la aplicación desde el equipo de desarrollo en HoloLens, seleccione **equipo remoto**. Si ya tiene una compilación existente en HoloLens, seleccione **sí** para instalar esta versión más reciente.  

   ![Implementación de equipos remotos para aplicaciones a HoloLens de Microsoft en Visual Studio](images/vs2015-remotedeployment.jpg)  
1. La aplicación se instalará y se iniciará automáticamente en HoloLens.

Después de instalar una aplicación, la encontrarás en la lista de **todas las aplicaciones** (**iniciar**  >  **todas las aplicaciones**).
