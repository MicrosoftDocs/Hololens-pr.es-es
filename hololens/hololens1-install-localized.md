---
title: Instalar versiones localizadas de HoloLens
description: Más información sobre cómo instalar las versiones en chino o japonés de HoloLens
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: high
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 9ccee2e11650926a5570967f1de5f6b341a17ae6
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2020
ms.locfileid: "10829665"
---
# Instalar versiones localizadas de HoloLens (1.ª generación)

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
