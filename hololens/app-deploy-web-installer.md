---
title: Cómo instalar aplicaciones a través de web Installer
description: Instalar aplicaciones a través de web Installer para el instalador de aplicaciones
keywords: App Management, App, hololens, instalador de aplicaciones, instalación Web
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
ms.openlocfilehash: 186cbefb2822455dcf922804ea09533b833b8663
ms.sourcegitcommit: a3e53f0e5070d0538f3ed74259914c59413eafd0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "11135453"
---
# Instalar aplicaciones desde una página web

Los usuarios pueden instalar una aplicación directamente desde un servidor Web. Esto usa el instalador de aplicaciones combinado con un método de distribución de instalación fácil de descargar e instalar. 

> [!IMPORTANT]
> Actualmente, esta característica solo avalible en Windows Insider compila 19041.1366 +. [Obtenga más información sobre cómo inscribirse en compilaciones de Windows Insider](hololens-insider.md).

## Cómo configurar esto:
1.  Asegúrate de que la aplicación esté correctamente configurada para instalarse.
1.  Siga estos [pasos para habilitar esta opción en una página web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage). 
1.  Elija un método de implementación de certificados. 
    1.  Los [paquetes de aprovisionamiento](hololens-provisioning.md) pueden aplicarse a dispositivos locales.
    1.  MDM se puede usar para [aplicar certificados con configuraciones de dispositivos](https://docs.microsoft.com/mem/intune/protect/certificates-configure).
    1.  Use el en el [Administrador de certificados](hololens-insider.md#certificate-manager)de dispositivo. 

## Experiencia de usuario final:
1.  El usuario recibe e instala el certificado en el dispositivo con un método previamente seleccionado. 
1.  El usuario visita la dirección URL creada a partir del paso anterior.

La aplicación se instalará en el dispositivo. Para buscar la aplicación, abre el **menú Inicio** y selecciona el botón **todas las aplicaciones** para encontrar tu aplicación. 

-   Para obtener ayuda con la solución de problemas de este método de instalación, visite [solucionar problemas del instalador](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)de la aplicación. 

> [!NOTE]
> No se admite la interfaz de usuario durante el proceso de actualización. Por lo tanto, no se admite la opción ShowPrompt de [esta página](https://docs.microsoft.com/windows/msix/app-installer/update-settings) ni las opciones relacionadas.
