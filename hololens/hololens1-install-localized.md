---
title: Instalación de versiones localizadas de HoloLens
description: Obtenga información sobre cómo instalar las versiones localizadas de HoloLens (1.ª generación), incluidas las versiones en chino y japonés.
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 74eb003aafd23218b90988abe113d35f1fc3035a
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2021
ms.locfileid: "108310278"
---
# <a name="install-localized-versions-of-hololens-1st-gen"></a>Instalación de versiones localizadas de HoloLens (1.ª generación)

Para cambiar a la versión en chino o japonés de HoloLens, deberá usar la Herramienta de recuperación de dispositivos Windows (WDRT) para descargar la compilación del idioma en un equipo y, a continuación, instalarla en HoloLens.

> [!IMPORTANT]
> El uso de WDRT para instalar las compilaciones en chino o japonés de HoloLens elimina los datos existentes, como los archivos personales y la configuración, de HoloLens. 

1. En el equipo, descargue e instale la Herramienta de recuperación de dispositivos [Windows (WDRT).](https://support.microsoft.com/help/12379)
1. Descargue el paquete para el idioma que desea en el equipo: [chino simplificado](https://aka.ms/hololensdownload-ch) o [japonés.](https://aka.ms/hololensdownload-jp)
1. Cuando finalice la descarga, seleccione **Explorador de archivos**  >  **Descargas.** Haga clic con el botón derecho en la carpeta comprimida que acaba de descargar y seleccione **Extraer toda**  >  **la extracción** para descomprimirla.
1. Conecte holoLens al equipo mediante el cable micro USB con el que se suministra. (Aunque haya estado usando otros cables para conectar holoLens, este funciona mejor).
1. Después de que la herramienta detecte automáticamente HoloLens, seleccione Microsoft HoloLens icono.
1. En la siguiente pantalla, seleccione **Selección** manual del paquete y seleccione el archivo de instalación que reside en la carpeta que   descomprimió en el paso 4. (Busque un archivo que tenga la extensión ".ffu"). 
1. Seleccione **Instalar software** y siga las instrucciones. 
1. Una vez instalada la compilación, la instalación de HoloLens se inicia automáticamente. Coloque el dispositivo y siga las instrucciones de configuración. 

Cuando haya terminado con el programa de instalación, vaya a Configuración Update & Security Programa Windows Insider y compruebe que está configurado para recibir las compilaciones de versión  >    >  preliminar más recientes. Al igual que las compilaciones de la versión preliminar en inglés, el Programa Windows Insider mantiene las versiones en chino y japonés de HoloLens actualizadas con las compilaciones de versión preliminar más recientes.

> [!NOTE]
>  
> - No puede usar la aplicación Configuración para cambiar el idioma del sistema entre inglés, japonés y chino. El flashing de una nueva compilación es la única manera admitida de cambiar el idioma del sistema del dispositivo.
> - Aunque puede usar el teclado Pinyin en pantalla para escribir texto chino simplificado o japonés, en este momento no se admite el uso de un teclado de hardware Bluetooth para escribir texto chino simplificado o japonés.  Sin embargo, en HoloLens chino o japonés, puede seguir usando un teclado Bluetooth para escribir en inglés (para alternar un teclado de hardware para escribir en inglés, presione la tecla ~).
