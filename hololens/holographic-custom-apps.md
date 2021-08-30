---
title: Administración de aplicaciones personalizadas HoloLens (1.ª generación)
description: Obtenga información sobre cómo instalar, desinstalar y cargar aplicaciones holográficas personalizadas en HoloLens dispositivos mediante Portal de dispositivos y Visual Studio.
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
ms.openlocfilehash: b6769c36f821ee3619ac9b62efd637ac561192bb
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2021
ms.locfileid: "123188855"
---
# <a name="manage-custom-apps-for-hololens-1st-gen"></a>Administración de aplicaciones personalizadas HoloLens (1.ª generación)

HoloLens admite muchas aplicaciones existentes de la Microsoft Store, así como nuevas aplicaciones creadas específicamente para HoloLens. Este artículo se centra en aplicaciones holográficas personalizadas.  

Para obtener más información sobre las aplicaciones de la tienda, vea [Administrar aplicaciones con la tienda](holographic-store-apps.md).

> [!IMPORTANT]
> La siguiente información se creó para la HoloLens (1.ª generación), también denominada HoloLens Developer Edition en ese momento. Por lo tanto, la transferencia local de aplicaciones a través del portal de dispositivos y la instalación de aplicaciones Visual Studio eran habituales en ese momento. En el caso de las implementaciones empresariales, no se recomienda habilitar el modo de desarrollador, que usan ambos métodos. Si está interesado en un método de implementación de aplicaciones seguras, revise nuestra administración [de aplicaciones: Información general.](app-deploy-overview.md)
>
> Si busca cualquiera de los métodos de instalación de aplicaciones para desarrolladores HoloLens 2 dispositivos, consulte:
>
> - [Portal de dispositivos: Instalación de una aplicación](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [Uso Visual Studio para implementar y depurar aplicaciones](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <a name="install-custom-apps"></a>Instalación de aplicaciones personalizadas

Puede instalar sus propias aplicaciones en HoloLens mediante el Portal de dispositivos o implementando las aplicaciones desde Visual Studio.

### <a name="installing-an-application-package-with-the-device-portal"></a>Instalación de un paquete de aplicación con el Portal de dispositivos

1. Establezca una conexión desde [Portal de dispositivos](/windows/mixed-reality/using-the-windows-device-portal) al destino HoloLens.

1. En el panel de navegación izquierdo, vaya a la **página** Aplicaciones.

1. En **Paquete de aplicación,** vaya al archivo .appx asociado a la aplicación.

   > [!IMPORTANT]
   > Asegúrese de hacer referencia a los archivos de certificado y dependencia asociados.

1. Seleccione **Ir**.

   > [!div class="mx-imgBorder"]
   > ![Instale el formulario de aplicación Windows Portal de dispositivos en Microsoft HoloLens.](images/deviceportal-appmanager.jpg)

### <a name="deploying-from-microsoft-visual-studio-2015"></a>Implementación desde Microsoft Visual Studio 2015

1. Abra la solución de Visual Studio aplicación (archivo .sln).

1. Abra las propiedades del **proyecto.**

1. Seleccione la siguiente configuración de compilación: **Master/x86/Remote Machine**.

1. Al seleccionar Equipo **remoto:**
   - Asegúrese de que la dirección apunta a la Wi-Fi IP de la HoloLens.
   - Establezca la autenticación **en Universal (protocolo sin cifrar).**
   
1. Compile la solución.

1. Para implementar la aplicación desde el equipo de desarrollo en la HoloLens, seleccione **Equipo remoto.** Si ya tiene una compilación existente en el HoloLens, seleccione **Sí** para instalar esta versión más reciente.  

   ![Implementación de máquina remota para que las aplicaciones Microsoft HoloLens en Visual Studio.](images/vs2015-remotedeployment.jpg)  
   
1. La aplicación se instalará e iniciará automáticamente en el HoloLens.

Después de instalar una aplicación, la encontrará en la lista Todas las **aplicaciones** **(Iniciar**  >  **todas las aplicaciones).**
