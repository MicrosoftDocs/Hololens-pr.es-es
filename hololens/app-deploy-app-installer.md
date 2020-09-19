---
title: Cómo cargar y instalar aplicaciones a través del instalador de aplicaciones de HoloLens 2
description: Descargar diapositivas e instalar aplicaciones a través de la interfaz de usuario
keywords: App Management, App, hololens, instalador de aplicaciones
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
ms.openlocfilehash: 2387c0eb65efc312db4eea7118f3cca44ce6d4b6
ms.sourcegitcommit: 4ad9b6c73913808175b1a448d2be9e33592f65af
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2020
ms.locfileid: "11027490"
---
# Instalar aplicaciones en HoloLens 2 a través del instalador de la aplicación

Ahora los usuarios pueden instalar aplicaciones a través de paquetes de appx, sin necesidad de habilitar el modo de desarrollador ni usar Device portal. Esta experiencia es sencilla para instalar aplicaciones en dispositivos locales o para compartir una aplicación con otra persona que no está familiarizada con otros métodos de instalación de aplicaciones en HoloLens. 

> [!IMPORTANT]
> Actualmente, esta característica solo avalible en Windows Insider compila 19041.1377 +. [Obtenga más información sobre cómo inscribirse en compilaciones de Windows Insider](hololens-insider.md).

> [!NOTE]
> La configuración de la solución de la aplicación debe ser **Master** o **Release** , ya que el instalador de la aplicación usará las dependencias de la tienda. Más información sobre cómo [crear paquetes de aplicaciones](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).

1.  Asegúrate de que tu dispositivo HoloLens 2 esté encendido y de que hayas iniciado sesión.
1.  En su equipo, navegue hasta la aplicación personalizada y copie SUAPLICACIÓN. appxbundle a yourdevicename\Internal Storage\Downloads. 
    Una vez que haya terminado de copiar el archivo, puede desconectar el dispositivo y finalizar la instalación más tarde.
1.  Desde tu dispositivo HoloLens 2 abre el **menú Inicio**, selecciona **todas las aplicaciones** e inicia la aplicación **Explorador de archivos** .
1.  Vaya a la carpeta descargas. Es posible que tenga que estar en el panel izquierdo de la aplicación, seleccione **este dispositivo** en primer lugar y, a continuación, vaya a descargas.
1.  Seleccione el archivo SUAPLICACIÓN. appxbundle. 
1.  Se iniciará el instalador de la aplicación. Seleccione el botón **instalar** para instalar la aplicación. 

La aplicación instalada se iniciará automáticamente al finalizar la instalación. 

![Instalación de MRTK ejemplos mediante el instalador de aplicaciones](images/hololens-app-installer-picture.jpg)

Si la aplicación no se instaló correctamente, compruebe lo siguiente:
-   Tu aplicación es una compilación de lanzamiento o maestra.
-   Estás [conectado a Internet](hololens-network.md).
-   Los [puntos de conexión de Microsoft Store](hololens-offline.md) están correctamente configurados.  
