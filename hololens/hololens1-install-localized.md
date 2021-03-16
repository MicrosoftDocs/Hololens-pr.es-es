---
title: Instalar versiones localizadas de HoloLens
description: Aprende a instalar las versiones localizadas de HoloLens (1.ª generación), incluidas las versiones en chino y japonés.
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
ms.sourcegitcommit: 01c0b0a789e156a9d29aaf6f61e36dfd09b8c01a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439016"
---
# <a name="install-localized-versions-of-hololens-1st-gen"></a>Instalar versiones localizadas de HoloLens (1.ª generación)

Para poder cambiar a la versión de HoloLens en chino o japonés de HoloLens, tendrás que usar la Windows Device Recovery Tool (WDRT) para descargar la compilación del idioma en un PC y, a continuación, instalarla en tu HoloLens.

> [!IMPORTANT]
> Al usar WDRT para instalar las compilaciones en chino o japonés de HoloLens, se eliminan los datos existentes, como los archivos personales y la configuración, de HoloLens. 

1. En tu PC, descarga e instala [la Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).
1. Descarga el paquete correspondiente al idioma que deseas en tu PC: [chino simplificado](https://aka.ms/hololensdownload-ch) o [japonés](https://aka.ms/hololensdownload-jp).
1. Cuando finalice la descarga, selecciona **Explorador de archivos** > **Descargas**. Haz clic con el botón derecho en la carpeta comprimida que acabas de descargar y selecciona **Extraer todo** > **Extraer** para descomprimirlo.
1. Conecta tu HoloLens a tu PC con el cable micro-USB con el que se incluye. (Incluso si has estado usando otros cables para conectar tu HoloLens, este es el que mejor funciona).
1. Una vez que la herramienta detecta automáticamente HoloLens, selecciona el icono de de Microsoft HoloLens.
1. En la siguiente pantalla, selecciona **Selección de paquete manual**  y elige el archivo de instalación que se encuentra en la carpeta que has descomprimido en el paso 4. (Busca un archivo que tenga la extensión ".ffu"). 
1. Selecciona **Instalar software** y sigue las instrucciones. 
1. Después de que se instale la compilación, la configuración de HoloLens se iniciará automáticamente. Ponte el dispositivo y sigue las instrucciones de configuración. 

Cuando hayas terminado con la configuración, ve a **Configuración** > **Actualización y seguridad** > **ProgramaWindowsInsider** y comprueba que dispones de la configuración para recibir las versiones preliminares más recientes. Al igual que las versiones preliminares en inglés, el Programa Windows Insider mantiene actualizadas las versiones en chino y japonés de HoloLens con las versiones preliminares más recientes.

> [!NOTE]
>  
> - No puedes usar la aplicación Configuración para cambiar el idioma del sistema entre inglés, japonés y chino. La instalación de la imagen de una nueva compilación es la única forma admitida de cambiar el idioma del sistema del dispositivo.
> - Aunque puedes usar el teclado Pinyin en pantalla para escribir texto en japonés o chino simplificado, el uso de un teclado de hardware Bluetooth para escribir texto en japonés o chino simplificado no se admite en este momento.  Sin embargo, en HoloLens en chino o en japonés, puedes seguir usando un teclado Bluetooth para escribir en inglés (para cambiar un teclado de hardware para escribir en inglés, presiona la tecla ~).
