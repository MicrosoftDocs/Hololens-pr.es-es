---
title: Instalación de versiones localizadas de HoloLens
description: Obtenga información sobre cómo instalar las versiones localizadas de HoloLens (1.ª generación), incluidas las versiones china y japonesa.
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
ms.openlocfilehash: fe29e4ed611f86764f0db576b1a8794fa0ceec3047cadd26f502209faadea8b0
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "115661809"
---
# <a name="install-localized-versions-of-hololens-1st-gen"></a>Instalación de versiones localizadas de HoloLens (1ª generación)

Para cambiar a la versión en chino o japonés de HoloLens, deberá usar la herramienta de recuperación de dispositivos de Windows (WDRT) para descargar la compilación del idioma en un equipo y, a continuación, instalarla en el HoloLens.

> [!IMPORTANT]
> El uso de WDRT para instalar las compilaciones en chino o japonés de HoloLens elimina los datos existentes, como los archivos personales y la configuración, de la HoloLens. 

1. En el equipo, descargue e instale el [Windows Device Recovery Tool (WDRT).](https://support.microsoft.com/help/12379)
1. Descargue el paquete del idioma que desea para el equipo: [chino simplificado](https://aka.ms/hololensdownload-ch) o [japonés.](https://aka.ms/hololensdownload-jp)
1. Cuando finalice la descarga, seleccione **Explorador de archivos**  >  **Descargas.** Haga clic con el botón derecho en la carpeta comprimida que acaba de descargar y seleccione **Extraer todo**  >  **extraer** para descomprimirla.
1. Conectar el HoloLens al equipo mediante el cable micro USB con el que se suministra. (Incluso si ha estado usando otros cables para conectar el HoloLens, este funciona mejor).
1. Después de que la herramienta detecte automáticamente el HoloLens, seleccione el icono Microsoft HoloLens aplicación.
1. En la siguiente pantalla, seleccione **Selección** manual del paquete y seleccione el archivo de instalación que reside en la carpeta que   descomprimió en el paso 4. (Busque un archivo que tenga la extensión ".ffu"). 
1. Seleccione **Instalar software** y siga las instrucciones. 
1. Una vez que se instala la compilación, HoloLens el programa de instalación se inicia automáticamente. Coloque en el dispositivo y siga las instrucciones de configuración. 

Cuando haya terminado con el programa de instalación, vaya **a** Configuración Update & Security Windows Programa Insider y compruebe que está configurado para recibir las compilaciones de versión preliminar  >    >  más recientes. Al igual que las compilaciones de la versión preliminar en inglés, Windows Programa Insider mantiene actualizadas las versiones en chino y japonés de HoloLens con las compilaciones de versión preliminar más recientes.

> [!NOTE]
>  
> - No se puede usar la aplicación Configuración para cambiar el idioma del sistema entre inglés, japonés y chino. El flashing de una nueva compilación es la única manera admitida de cambiar el idioma del sistema del dispositivo.
> - Aunque puede usar el teclado Pinyin en pantalla para escribir texto chino simplificado o japonés, en este momento no se admite el uso de un teclado de hardware Bluetooth para escribir texto chino simplificado o japonés.  Sin embargo, en chino o japonés HoloLens, puede seguir usando un teclado Bluetooth para escribir en inglés (para alternar un teclado de hardware para escribir en inglés, presione la tecla ~).
