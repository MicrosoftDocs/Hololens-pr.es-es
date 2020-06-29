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
# <span data-ttu-id="7a6a3-103">Instalar versiones localizadas de HoloLens (1.ª generación)</span><span class="sxs-lookup"><span data-stu-id="7a6a3-103">Install localized versions of HoloLens (1st gen)</span></span>

<span data-ttu-id="7a6a3-104">Para poder cambiar a la versión de HoloLens en chino o japonés de HoloLens, tendrás que usar la Windows Device Recovery Tool (WDRT) para descargar la compilación del idioma en un PC y, a continuación, instalarla en tu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="7a6a3-104">In order to switch to the Chinese or Japanese version of HoloLens, you’ll need to use the Windows Device Recovery Tool (WDRT) to download the build for the language on a PC and then install it on your HoloLens.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7a6a3-105">Al usar WDRT para instalar las compilaciones en chino o japonés de HoloLens, se eliminan los datos existentes, como los archivos personales y la configuración, de HoloLens.</span><span class="sxs-lookup"><span data-stu-id="7a6a3-105">Using WDRT to install the Chinese or Japanese builds of HoloLens deletes existing data, such as personal files and settings, from your HoloLens.</span></span> 

1. <span data-ttu-id="7a6a3-106">En tu PC, descarga e instala [la Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span><span class="sxs-lookup"><span data-stu-id="7a6a3-106">On your PC, download and install [the Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="7a6a3-107">Descarga el paquete correspondiente al idioma que deseas en tu PC: [chino simplificado](https://aka.ms/hololensdownload-ch) o [japonés](https://aka.ms/hololensdownload-jp).</span><span class="sxs-lookup"><span data-stu-id="7a6a3-107">Download the package for the language you want to your PC:  [Simplified Chinese](https://aka.ms/hololensdownload-ch) or [Japanese](https://aka.ms/hololensdownload-jp).</span></span>
1. <span data-ttu-id="7a6a3-108">Cuando finalice la descarga, selecciona **Explorador de archivos** > **Descargas**.</span><span class="sxs-lookup"><span data-stu-id="7a6a3-108">When the download finishes, select **File Explorer** > **Downloads**.</span></span> <span data-ttu-id="7a6a3-109">Haz clic con el botón derecho en la carpeta comprimida que acabas de descargar y selecciona **Extraer todo** > **Extraer** para descomprimirlo.</span><span class="sxs-lookup"><span data-stu-id="7a6a3-109">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="7a6a3-110">Conecta tu HoloLens a tu PC con el cable micro-USB con el que se incluye.</span><span class="sxs-lookup"><span data-stu-id="7a6a3-110">Connect your HoloLens to your PC using the micro-USB cable that it shipped with.</span></span> <span data-ttu-id="7a6a3-111">(Incluso si has estado usando otros cables para conectar tu HoloLens, este es el que mejor funciona).</span><span class="sxs-lookup"><span data-stu-id="7a6a3-111">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="7a6a3-112">Una vez que la herramienta detecta automáticamente HoloLens, selecciona el icono de de Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="7a6a3-112">After the tool automatically detects your HoloLens, select the Microsoft HoloLens tile.</span></span>
1. <span data-ttu-id="7a6a3-113">En la siguiente pantalla, selecciona **Selección de paquete manual**  y elige el archivo de instalación que se encuentra en la carpeta que has descomprimido en el paso 4.</span><span class="sxs-lookup"><span data-stu-id="7a6a3-113">On the next screen, select **Manual package selection** and select the installation file that resides in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="7a6a3-114">(Busca un archivo que tenga la extensión ".ffu").</span><span class="sxs-lookup"><span data-stu-id="7a6a3-114">(Look for a file that has the extension “.ffu”.)</span></span> 
1. <span data-ttu-id="7a6a3-115">Selecciona **Instalar software** y sigue las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="7a6a3-115">Select **Install software** and follow the instructions.</span></span> 
1. <span data-ttu-id="7a6a3-116">Después de que se instale la compilación, la configuración de HoloLens se iniciará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="7a6a3-116">After the build installs, HoloLens setup automatically starts.</span></span> <span data-ttu-id="7a6a3-117">Ponte el dispositivo y sigue las instrucciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="7a6a3-117">Put on the device and follow the setup directions.</span></span> 

<span data-ttu-id="7a6a3-118">Cuando hayas terminado con la configuración, ve a **Configuración** > **Actualización y seguridad** > **ProgramaWindowsInsider** y comprueba que dispones de la configuración para recibir las versiones preliminares más recientes.</span><span class="sxs-lookup"><span data-stu-id="7a6a3-118">When you’re done with setup, go to **Settings** > **Update & Security** > **Windows Insider Program**, and check that you’re configured to receive the latest preview builds.</span></span> <span data-ttu-id="7a6a3-119">Al igual que las versiones preliminares en inglés, el Programa Windows Insider mantiene actualizadas las versiones en chino y japonés de HoloLens con las versiones preliminares más recientes.</span><span class="sxs-lookup"><span data-stu-id="7a6a3-119">Like the English preview builds, the Windows Insider Program keeps the Chinese and Japanese versions of HoloLens up-to-date with the latest preview builds.</span></span>

> [!NOTE]
>  
> - <span data-ttu-id="7a6a3-120">No puedes usar la aplicación Configuración para cambiar el idioma del sistema entre inglés, japonés y chino.</span><span class="sxs-lookup"><span data-stu-id="7a6a3-120">You can’t use the Settings app to change the system language between English, Japanese, and Chinese.</span></span> <span data-ttu-id="7a6a3-121">La instalación de la imagen de una nueva compilación es la única forma admitida de cambiar el idioma del sistema del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7a6a3-121">Flashing a new build is the only supported way to change the device system language.</span></span>
> - <span data-ttu-id="7a6a3-122">Aunque puedes usar el teclado Pinyin en pantalla para escribir texto en japonés o chino simplificado, el uso de un teclado de hardware Bluetooth para escribir texto en japonés o chino simplificado no se admite en este momento.</span><span class="sxs-lookup"><span data-stu-id="7a6a3-122">While you can use the on-screen Pinyin keyboard to enter Simplified Chinese or Japanese text, using a Bluetooth hardware keyboard to type Simplified Chinese or Japanese text is not supported at this time.</span></span>  <span data-ttu-id="7a6a3-123">Sin embargo, en HoloLens en chino o en japonés, puedes seguir usando un teclado Bluetooth para escribir en inglés (para cambiar un teclado de hardware para escribir en inglés, presiona la tecla ~).</span><span class="sxs-lookup"><span data-stu-id="7a6a3-123">However, on Chinese or Japanese HoloLens, you can continue to use a Bluetooth keyboard to type in English (to toggle a hardware keyboard to type in English, press the ~ key).</span></span>
