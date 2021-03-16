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
# <a name="install-localized-versions-of-hololens-1st-gen"></a><span data-ttu-id="04886-103">Instalar versiones localizadas de HoloLens (1.ª generación)</span><span class="sxs-lookup"><span data-stu-id="04886-103">Install localized versions of HoloLens (1st gen)</span></span>

<span data-ttu-id="04886-104">Para poder cambiar a la versión de HoloLens en chino o japonés de HoloLens, tendrás que usar la Windows Device Recovery Tool (WDRT) para descargar la compilación del idioma en un PC y, a continuación, instalarla en tu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="04886-104">In order to switch to the Chinese or Japanese version of HoloLens, you’ll need to use the Windows Device Recovery Tool (WDRT) to download the build for the language on a PC and then install it on your HoloLens.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="04886-105">Al usar WDRT para instalar las compilaciones en chino o japonés de HoloLens, se eliminan los datos existentes, como los archivos personales y la configuración, de HoloLens.</span><span class="sxs-lookup"><span data-stu-id="04886-105">Using WDRT to install the Chinese or Japanese builds of HoloLens deletes existing data, such as personal files and settings, from your HoloLens.</span></span> 

1. <span data-ttu-id="04886-106">En tu PC, descarga e instala [la Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span><span class="sxs-lookup"><span data-stu-id="04886-106">On your PC, download and install [the Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="04886-107">Descarga el paquete correspondiente al idioma que deseas en tu PC: [chino simplificado](https://aka.ms/hololensdownload-ch) o [japonés](https://aka.ms/hololensdownload-jp).</span><span class="sxs-lookup"><span data-stu-id="04886-107">Download the package for the language you want to your PC:  [Simplified Chinese](https://aka.ms/hololensdownload-ch) or [Japanese](https://aka.ms/hololensdownload-jp).</span></span>
1. <span data-ttu-id="04886-108">Cuando finalice la descarga, selecciona **Explorador de archivos** > **Descargas**.</span><span class="sxs-lookup"><span data-stu-id="04886-108">When the download finishes, select **File Explorer** > **Downloads**.</span></span> <span data-ttu-id="04886-109">Haz clic con el botón derecho en la carpeta comprimida que acabas de descargar y selecciona **Extraer todo** > **Extraer** para descomprimirlo.</span><span class="sxs-lookup"><span data-stu-id="04886-109">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="04886-110">Conecta tu HoloLens a tu PC con el cable micro-USB con el que se incluye.</span><span class="sxs-lookup"><span data-stu-id="04886-110">Connect your HoloLens to your PC using the micro-USB cable that it shipped with.</span></span> <span data-ttu-id="04886-111">(Incluso si has estado usando otros cables para conectar tu HoloLens, este es el que mejor funciona).</span><span class="sxs-lookup"><span data-stu-id="04886-111">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="04886-112">Una vez que la herramienta detecta automáticamente HoloLens, selecciona el icono de de Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="04886-112">After the tool automatically detects your HoloLens, select the Microsoft HoloLens tile.</span></span>
1. <span data-ttu-id="04886-113">En la siguiente pantalla, selecciona **Selección de paquete manual**  y elige el archivo de instalación que se encuentra en la carpeta que has descomprimido en el paso 4.</span><span class="sxs-lookup"><span data-stu-id="04886-113">On the next screen, select **Manual package selection** and select the installation file that resides in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="04886-114">(Busca un archivo que tenga la extensión ".ffu").</span><span class="sxs-lookup"><span data-stu-id="04886-114">(Look for a file that has the extension “.ffu”.)</span></span> 
1. <span data-ttu-id="04886-115">Selecciona **Instalar software** y sigue las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="04886-115">Select **Install software** and follow the instructions.</span></span> 
1. <span data-ttu-id="04886-116">Después de que se instale la compilación, la configuración de HoloLens se iniciará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="04886-116">After the build installs, HoloLens setup automatically starts.</span></span> <span data-ttu-id="04886-117">Ponte el dispositivo y sigue las instrucciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="04886-117">Put on the device and follow the setup directions.</span></span> 

<span data-ttu-id="04886-118">Cuando hayas terminado con la configuración, ve a **Configuración** > **Actualización y seguridad** > **ProgramaWindowsInsider** y comprueba que dispones de la configuración para recibir las versiones preliminares más recientes.</span><span class="sxs-lookup"><span data-stu-id="04886-118">When you’re done with setup, go to **Settings** > **Update & Security** > **Windows Insider Program**, and check that you’re configured to receive the latest preview builds.</span></span> <span data-ttu-id="04886-119">Al igual que las versiones preliminares en inglés, el Programa Windows Insider mantiene actualizadas las versiones en chino y japonés de HoloLens con las versiones preliminares más recientes.</span><span class="sxs-lookup"><span data-stu-id="04886-119">Like the English preview builds, the Windows Insider Program keeps the Chinese and Japanese versions of HoloLens up-to-date with the latest preview builds.</span></span>

> [!NOTE]
>  
> - <span data-ttu-id="04886-120">No puedes usar la aplicación Configuración para cambiar el idioma del sistema entre inglés, japonés y chino.</span><span class="sxs-lookup"><span data-stu-id="04886-120">You can’t use the Settings app to change the system language between English, Japanese, and Chinese.</span></span> <span data-ttu-id="04886-121">La instalación de la imagen de una nueva compilación es la única forma admitida de cambiar el idioma del sistema del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="04886-121">Flashing a new build is the only supported way to change the device system language.</span></span>
> - <span data-ttu-id="04886-122">Aunque puedes usar el teclado Pinyin en pantalla para escribir texto en japonés o chino simplificado, el uso de un teclado de hardware Bluetooth para escribir texto en japonés o chino simplificado no se admite en este momento.</span><span class="sxs-lookup"><span data-stu-id="04886-122">While you can use the on-screen Pinyin keyboard to enter Simplified Chinese or Japanese text, using a Bluetooth hardware keyboard to type Simplified Chinese or Japanese text is not supported at this time.</span></span>  <span data-ttu-id="04886-123">Sin embargo, en HoloLens en chino o en japonés, puedes seguir usando un teclado Bluetooth para escribir en inglés (para cambiar un teclado de hardware para escribir en inglés, presiona la tecla ~).</span><span class="sxs-lookup"><span data-stu-id="04886-123">However, on Chinese or Japanese HoloLens, you can continue to use a Bluetooth keyboard to type in English (to toggle a hardware keyboard to type in English, press the ~ key).</span></span>
