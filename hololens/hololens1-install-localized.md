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
# <a name="install-localized-versions-of-hololens-1st-gen"></a><span data-ttu-id="46174-103">Instalación de versiones localizadas de HoloLens (1.ª generación)</span><span class="sxs-lookup"><span data-stu-id="46174-103">Install localized versions of HoloLens (1st gen)</span></span>

<span data-ttu-id="46174-104">Para cambiar a la versión en chino o japonés de HoloLens, deberá usar la Herramienta de recuperación de dispositivos Windows (WDRT) para descargar la compilación del idioma en un equipo y, a continuación, instalarla en HoloLens.</span><span class="sxs-lookup"><span data-stu-id="46174-104">In order to switch to the Chinese or Japanese version of HoloLens, you’ll need to use the Windows Device Recovery Tool (WDRT) to download the build for the language on a PC and then install it on your HoloLens.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="46174-105">El uso de WDRT para instalar las compilaciones en chino o japonés de HoloLens elimina los datos existentes, como los archivos personales y la configuración, de HoloLens.</span><span class="sxs-lookup"><span data-stu-id="46174-105">Using WDRT to install the Chinese or Japanese builds of HoloLens deletes existing data, such as personal files and settings, from your HoloLens.</span></span> 

1. <span data-ttu-id="46174-106">En el equipo, descargue e instale la Herramienta de recuperación de dispositivos [Windows (WDRT).](https://support.microsoft.com/help/12379)</span><span class="sxs-lookup"><span data-stu-id="46174-106">On your PC, download and install [the Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="46174-107">Descargue el paquete para el idioma que desea en el equipo: [chino simplificado](https://aka.ms/hololensdownload-ch) o [japonés.](https://aka.ms/hololensdownload-jp)</span><span class="sxs-lookup"><span data-stu-id="46174-107">Download the package for the language you want to your PC:  [Simplified Chinese](https://aka.ms/hololensdownload-ch) or [Japanese](https://aka.ms/hololensdownload-jp).</span></span>
1. <span data-ttu-id="46174-108">Cuando finalice la descarga, seleccione **Explorador de archivos**  >  **Descargas.**</span><span class="sxs-lookup"><span data-stu-id="46174-108">When the download finishes, select **File Explorer** > **Downloads**.</span></span> <span data-ttu-id="46174-109">Haga clic con el botón derecho en la carpeta comprimida que acaba de descargar y seleccione **Extraer toda**  >  **la extracción** para descomprimirla.</span><span class="sxs-lookup"><span data-stu-id="46174-109">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="46174-110">Conecte holoLens al equipo mediante el cable micro USB con el que se suministra.</span><span class="sxs-lookup"><span data-stu-id="46174-110">Connect your HoloLens to your PC using the micro-USB cable that it shipped with.</span></span> <span data-ttu-id="46174-111">(Aunque haya estado usando otros cables para conectar holoLens, este funciona mejor).</span><span class="sxs-lookup"><span data-stu-id="46174-111">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="46174-112">Después de que la herramienta detecte automáticamente HoloLens, seleccione Microsoft HoloLens icono.</span><span class="sxs-lookup"><span data-stu-id="46174-112">After the tool automatically detects your HoloLens, select the Microsoft HoloLens tile.</span></span>
1. <span data-ttu-id="46174-113">En la siguiente pantalla, seleccione **Selección** manual del paquete y seleccione el archivo de instalación que reside en la carpeta que   descomprimió en el paso 4.</span><span class="sxs-lookup"><span data-stu-id="46174-113">On the next screen, select **Manual package selection** and select the installation file that resides in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="46174-114">(Busque un archivo que tenga la extensión ".ffu").</span><span class="sxs-lookup"><span data-stu-id="46174-114">(Look for a file that has the extension “.ffu”.)</span></span> 
1. <span data-ttu-id="46174-115">Seleccione **Instalar software** y siga las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="46174-115">Select **Install software** and follow the instructions.</span></span> 
1. <span data-ttu-id="46174-116">Una vez instalada la compilación, la instalación de HoloLens se inicia automáticamente.</span><span class="sxs-lookup"><span data-stu-id="46174-116">After the build installs, HoloLens setup automatically starts.</span></span> <span data-ttu-id="46174-117">Coloque el dispositivo y siga las instrucciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="46174-117">Put on the device and follow the setup directions.</span></span> 

<span data-ttu-id="46174-118">Cuando haya terminado con el programa de instalación, vaya a Configuración Update & Security Programa Windows Insider y compruebe que está configurado para recibir las compilaciones de versión  >    >  preliminar más recientes.</span><span class="sxs-lookup"><span data-stu-id="46174-118">When you’re done with setup, go to **Settings** > **Update & Security** > **Windows Insider Program**, and check that you’re configured to receive the latest preview builds.</span></span> <span data-ttu-id="46174-119">Al igual que las compilaciones de la versión preliminar en inglés, el Programa Windows Insider mantiene las versiones en chino y japonés de HoloLens actualizadas con las compilaciones de versión preliminar más recientes.</span><span class="sxs-lookup"><span data-stu-id="46174-119">Like the English preview builds, the Windows Insider Program keeps the Chinese and Japanese versions of HoloLens up-to-date with the latest preview builds.</span></span>

> [!NOTE]
>  
> - <span data-ttu-id="46174-120">No puede usar la aplicación Configuración para cambiar el idioma del sistema entre inglés, japonés y chino.</span><span class="sxs-lookup"><span data-stu-id="46174-120">You can’t use the Settings app to change the system language between English, Japanese, and Chinese.</span></span> <span data-ttu-id="46174-121">El flashing de una nueva compilación es la única manera admitida de cambiar el idioma del sistema del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="46174-121">Flashing a new build is the only supported way to change the device system language.</span></span>
> - <span data-ttu-id="46174-122">Aunque puede usar el teclado Pinyin en pantalla para escribir texto chino simplificado o japonés, en este momento no se admite el uso de un teclado de hardware Bluetooth para escribir texto chino simplificado o japonés.</span><span class="sxs-lookup"><span data-stu-id="46174-122">While you can use the on-screen Pinyin keyboard to enter Simplified Chinese or Japanese text, using a Bluetooth hardware keyboard to type Simplified Chinese or Japanese text is not supported at this time.</span></span>  <span data-ttu-id="46174-123">Sin embargo, en HoloLens chino o japonés, puede seguir usando un teclado Bluetooth para escribir en inglés (para alternar un teclado de hardware para escribir en inglés, presione la tecla ~).</span><span class="sxs-lookup"><span data-stu-id="46174-123">However, on Chinese or Japanese HoloLens, you can continue to use a Bluetooth keyboard to type in English (to toggle a hardware keyboard to type in English, press the ~ key).</span></span>
