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
# Administrar aplicaciones personalizadas para HoloLens (1.ª generación)

HoloLens soporta muchas aplicaciones existentes de Microsoft Store, así como nuevas aplicaciones construidas específicamente para HoloLens. Este artículo se centra en aplicaciones holográficas personalizadas.  

Para obtener más información acerca de las aplicaciones de la Tienda, consulta [Administrar aplicaciones con la tienda.](holographic-store-apps.md)

> [!IMPORTANT]
> La siguiente información se creó para HoloLens (1.ª generación), también denominada HoloLens Developer Edition en ese momento. Por lo tanto, la instalación local de aplicaciones a través del portal de dispositivos y la instalación de aplicaciones Visual Studio era habitual en ese momento. Para las implementaciones empresariales no recomendamos habilitar el modo de desarrollador, que usan ambos métodos. Si está interesado en un método seguro de implementación de aplicaciones, revise nuestra administración [de aplicaciones: Información general.](app-deploy-overview.md)
>
> Si está buscando cualquiera de los métodos de instalación de aplicaciones para dispositivos HoloLens 2, consulte:
> - [Device Portal: Instalar una aplicación](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [Usar Visual Studio para implementar y depurar aplicaciones](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## Instalar aplicaciones personalizadas

Puedes instalar tus propias aplicaciones en HoloLens mediante Device Portal o implementando las aplicaciones desde Visual Studio.

### Instalación de un paquete de aplicación con Device Portal

1. Establecer una conexión desde [Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) al HoloLens de destino.

1. En el panel de navegación izquierdo, vaya a la **página** Aplicaciones.

1. En **Paquete de la** aplicación, busca el archivo .appx asociado a la aplicación.

   > [!IMPORTANT]
   > Asegúrate de hacer referencia a cualquier archivo de certificado y dependencia asociado.

1. Seleccione **Ir**.

   > [!div class="mx-imgBorder"]
   > ![Instalar el formulario de aplicación en Windows Device Portal en Microsoft HoloLens](images/deviceportal-appmanager.jpg)

### Implementación desde Microsoft Visual Studio 2015

1. Abre la solución de Visual Studio aplicación (archivo .sln).

1. Abra las propiedades del **proyecto.**

1. Seleccione la siguiente configuración de compilación: **Maestro/x86/Máquina remota.**

1. Al seleccionar Equipo **remoto:**
   - Asegúrese de que la dirección apunta a la Wi-Fi IP de su HoloLens.
   - Establezca la **autenticación en Universal (protocolo sin cifrar).**
   
1. Cree la solución.

1. Para implementar la aplicación desde el equipo de desarrollo a HoloLens, selecciona **Máquina remota.** Si ya tienes una compilación existente en HoloLens, selecciona **Sí** para instalar esta versión más reciente.  

   ![Implementación de máquina remota para aplicaciones en Microsoft HoloLens en Visual Studio](images/vs2015-remotedeployment.jpg)  
   
1. La aplicación se instalará y se iniciará automáticamente en holoLens.

Después de instalar una aplicación, la encontrarás en **** la lista Todas las aplicaciones **(Iniciar**  >  **todas las aplicaciones).**
