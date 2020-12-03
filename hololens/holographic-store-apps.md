---
title: Buscar, instalar y desinstalar aplicaciones
description: La Microsoft Store es su fuente de aplicaciones y juegos que funcionan con HoloLens.  Aprenda más sobre cómo encontrar, instalar y desinstalar aplicaciones holográficas.
ms.assetid: cbe9aa3a-884f-4a92-bf54-8d4917bc3435
ms.reviewer: v-miegge
ms.date: 10/27/2020
manager: jarrettr
keywords: hololens, tienda, uwp, aplicación, instalación
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 06768203459827a83d8b6e891dfc8c46e33c3da2
ms.sourcegitcommit: 1f37a06cde037f3acdc4ef3767a9384953d97c33
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2020
ms.locfileid: "11194870"
---
# <span data-ttu-id="3596f-105">Encontrar, instalar y desinstalar aplicaciones de Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="3596f-105">Find, install, and uninstall applications from the Microsoft Store</span></span>

<span data-ttu-id="3596f-106">Microsoft Store es su fuente de información para aplicaciones y juegos que funcionan con HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3596f-106">The Microsoft Store is your go-to source for apps and games that work with HoloLens.</span></span> <span data-ttu-id="3596f-107">Cuando vaya a la tienda en su HoloLens, cualquier aplicación que vea allí funcionará con él.</span><span class="sxs-lookup"><span data-stu-id="3596f-107">When you go to the Store on your HoloLens, any apps you see there will run on it.</span></span>

<span data-ttu-id="3596f-108">Las aplicaciones de HoloLens usan la vista 2D o la vista holográfica.</span><span class="sxs-lookup"><span data-stu-id="3596f-108">Apps on HoloLens use either 2D view or holographic view.</span></span> <span data-ttu-id="3596f-109">Las aplicaciones que usan la vista 2D se parecen a las ventanas y pueden ser posicionadas a su alrededor.</span><span class="sxs-lookup"><span data-stu-id="3596f-109">Apps that use 2D view look like windows and can be positioned all around you.</span></span> <span data-ttu-id="3596f-110">Las aplicaciones que utilizan la vista holográfica lo rodean y se convierten en las únicas aplicaciones visibles para usted.</span><span class="sxs-lookup"><span data-stu-id="3596f-110">Apps that use holographic view surround you and become the only app you see.</span></span>

<span data-ttu-id="3596f-111">HoloLens soporta muchas aplicaciones existentes de Microsoft Store, así como nuevas aplicaciones construidas específicamente para HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3596f-111">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span>  <span data-ttu-id="3596f-112">Este artículo se centra en las aplicaciones holográficas de Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="3596f-112">This article focuses on holographic applications from the Microsoft Store.</span></span>

<span data-ttu-id="3596f-113">Para aprender más acerca de la instalación y ejecución de aplicaciones personalizadas, lea[ Aplicaciones holográficas personalizadas](holographic-custom-apps.md).</span><span class="sxs-lookup"><span data-stu-id="3596f-113">To learn more about installing and running custom apps, read [Custom holographic applications](holographic-custom-apps.md).</span></span>

## <span data-ttu-id="3596f-114">Buscar aplicaciones</span><span class="sxs-lookup"><span data-stu-id="3596f-114">Find apps</span></span>

<span data-ttu-id="3596f-115">Abra el Microsoft Store desde el menú **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="3596f-115">Open the Microsoft Store from the **Start** menu.</span></span> <span data-ttu-id="3596f-116">Entonces busque aplicaciones y juegos.</span><span class="sxs-lookup"><span data-stu-id="3596f-116">Then browse for apps and games.</span></span> <span data-ttu-id="3596f-117">Puede usar [comandos de voz](hololens-cortana.md) para buscar diciendo "Buscar", una vez que se abre la ventana de búsqueda, diga "Iniciar dictado" y, a continuación, cuando se le solicite, empiece por indicar los términos de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="3596f-117">You can use [voice commands](hololens-cortana.md) to search by saying "Search", once the search window opens say "Start dictating" and then when prompted begin saying your search terms.</span></span>

> [!NOTE]
> <span data-ttu-id="3596f-118">Los requisitos del sistema para los dispositivos HoloLens se basan en la arquitectura de la compilación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3596f-118">The System Requirements for HoloLens devices are based on the architecture of the app build.</span></span> <span data-ttu-id="3596f-119">Si una compilación de la aplicación para HoloLens (1 ª gen) no se ha actualizado con una UWP más reciente en la tienda para incluir el paquete de arquitectura ARM, no estará disponible para los dispositivos HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="3596f-119">If an app build for HoloLens (1st gen) has not been updated with to a newer UWP in the store to include the ARM architecture package, then it will not be available for HoloLens 2 devices.</span></span> <span data-ttu-id="3596f-120">Del mismo modo, si una aplicación de HoloLens 2 no incluye el paquete de arquitectura x86, no estará disponible para los dispositivos HoloLens (1. ª gen).</span><span class="sxs-lookup"><span data-stu-id="3596f-120">Likewise, if a HoloLens 2 app does not include the x86 architecture package, it will not be available for HoloLens (1st gen) devices.</span></span> <span data-ttu-id="3596f-121">Arquitecturas de dispositivos HoloLens:</span><span class="sxs-lookup"><span data-stu-id="3596f-121">HoloLens device architectures:</span></span>
> - <span data-ttu-id="3596f-122">x86 = HoloLens (1ª generación)</span><span class="sxs-lookup"><span data-stu-id="3596f-122">x86 = HoloLens (1st gen)</span></span>
> - <span data-ttu-id="3596f-123">ARM = HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="3596f-123">ARM = HoloLens 2</span></span>

> [!NOTE]
> <span data-ttu-id="3596f-124">El 12 de enero de 2021, las siguientes aplicaciones dejarán de recibir soporte técnico para los dispositivos HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3596f-124">On January 12, 2021 the following apps will reach End of Support on HoloLens devices.</span></span> <span data-ttu-id="3596f-125">Te recomendamos que uses el vínculo siguiente en el dispositivo para usar la versión Web de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3596f-125">We encourage you to use the following link on your device to use the web version of the app.</span></span>

| <span data-ttu-id="3596f-126">Aplicación</span><span class="sxs-lookup"><span data-stu-id="3596f-126">App</span></span>        | <span data-ttu-id="3596f-127">Vínculo</span><span class="sxs-lookup"><span data-stu-id="3596f-127">Link</span></span>                                          |
|------------|-----------------------------------------------|
| <span data-ttu-id="3596f-128">Excel Mobile</span><span class="sxs-lookup"><span data-stu-id="3596f-128">Excel mobile</span></span>      | https://office.live.com/start/Excel.aspx      |
| <span data-ttu-id="3596f-129">Word Mobile</span><span class="sxs-lookup"><span data-stu-id="3596f-129">Word mobile</span></span>       | https://office.live.com/start/Word.aspx       |
| <span data-ttu-id="3596f-130">PowerPoint Mobile</span><span class="sxs-lookup"><span data-stu-id="3596f-130">PowerPoint mobile</span></span> | https://office.live.com/start/PowerPoint.aspx |

## <span data-ttu-id="3596f-131">Instalar aplicaciones</span><span class="sxs-lookup"><span data-stu-id="3596f-131">Install apps</span></span>

<span data-ttu-id="3596f-132">Para descargar aplicaciones, tendrá que iniciar sesión con una cuenta de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3596f-132">To download apps, you'll need to be signed in with a Microsoft account.</span></span> <span data-ttu-id="3596f-133">Algunas aplicaciones son gratuitas y pueden ser descargadas de inmediato.</span><span class="sxs-lookup"><span data-stu-id="3596f-133">Some apps are free and can be downloaded right away.</span></span> <span data-ttu-id="3596f-134">Las aplicaciones que requieren una compra requieren que inicie sesión en la tienda con su cuenta de Microsoft y que tenga un método de pago válido.</span><span class="sxs-lookup"><span data-stu-id="3596f-134">Apps that require a purchase require you to be signed in to the Store with your Microsoft account and have a valid payment method.</span></span>
> [!NOTE]
> <span data-ttu-id="3596f-135">La cuenta que utilice en Microsoft Store no tiene que ser la misma que la cuenta con la que ha iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="3596f-135">The account you use on Microsoft Store does not have to be the same as the account you are signed in with.</span></span> <span data-ttu-id="3596f-136">Si está usando una cuenta profesional o educativa en HoloLens, tal vez tendrá que iniciar sesión con su cuenta personal en la aplicación de la Tienda para hacer una compra.</span><span class="sxs-lookup"><span data-stu-id="3596f-136">If you are using a Work or School account on your HoloLens then you may need to sign in with your personal account in the Store App to make a purchase.</span></span>

<span data-ttu-id="3596f-137">Para configurar un método de pago, vaya a [account.microsoft.com](https://account.microsoft.com/) y seleccione **Pago y facturación** > **Opciones de pago** > **Agregar una opción de pago**.</span><span class="sxs-lookup"><span data-stu-id="3596f-137">To set up a payment method, go to [account.microsoft.com](https://account.microsoft.com/) and select **Payment & billing** > **Payment options** > **Add a payment option**.</span></span>

1. <span data-ttu-id="3596f-138">Para abrir el [menú **Inicio**](holographic-home.md), realice un [Gesto Inicio ](https://docs.microsoft.com/hololens/hololens2-basic-usage#start-gesture)o un gesto de [eclosión](hololens1-basic-usage.md) en HoloLens (1era generación).</span><span class="sxs-lookup"><span data-stu-id="3596f-138">To open the [**Start** menu](holographic-home.md), perform a [Start gesture](https://docs.microsoft.com/hololens/hololens2-basic-usage#start-gesture) or [bloom](hololens1-basic-usage.md) gesture on HoloLens (1st gen).</span></span>
1. <span data-ttu-id="3596f-139">Seleccionar la aplicación Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="3596f-139">Select the Microsoft Store app.</span></span> <span data-ttu-id="3596f-140">Una vez que la aplicación de la tienda se abra:</span><span class="sxs-lookup"><span data-stu-id="3596f-140">Once the Store app opens:</span></span>
   1. <span data-ttu-id="3596f-141">Utilice la barra de búsqueda para buscar cualquier aplicación deseada.</span><span class="sxs-lookup"><span data-stu-id="3596f-141">Use the search bar to look for any desired applications.</span></span> 
   1. <span data-ttu-id="3596f-142">Seleccione aplicaciones esenciales o aplicaciones hechas específicamente para el HoloLens de una de las categorías curadas.</span><span class="sxs-lookup"><span data-stu-id="3596f-142">Select essential apps or apps made specifically for HoloLens from one of the curated categories.</span></span>
   1. <span data-ttu-id="3596f-143">En la parte superior derecha de la aplicación la Tienda, seleccione el botón **"..."** y luego seleccione **Mi biblioteca** para ver las aplicaciones compradas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="3596f-143">On the top right of the Store app, select the **"..."** button and then select **My Library** to view any previously purchased apps.</span></span>
1. <span data-ttu-id="3596f-144">Seleccione **Obtener**o**Instalar**en la página de la aplicación (es posible que se requiera una compra).</span><span class="sxs-lookup"><span data-stu-id="3596f-144">Select **Get** or **Install** on the application's page (a purchase may be required).</span></span>

## <span data-ttu-id="3596f-145">Actualizar aplicaciones</span><span class="sxs-lookup"><span data-stu-id="3596f-145">Update Apps</span></span>
<span data-ttu-id="3596f-146">Para actualizar una aplicación que haya instalado desde la aplicación Microsoft Store, puede hacerlo desde la misma aplicación Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="3596f-146">To update an app you have installed from the Microsoft Store app you can also update the same app from the Microsoft Store app.</span></span> <span data-ttu-id="3596f-147">Esto también aplica a las aplicaciones instaladas desde Microsoft Store para Empresas.</span><span class="sxs-lookup"><span data-stu-id="3596f-147">This also applies to apps installed for Microsoft Store for Business.</span></span> 
1. <span data-ttu-id="3596f-148">Para abrir el [menú **Inicio**](holographic-home.md), realice un [Gesto Inicio ](https://docs.microsoft.com/hololens/hololens2-basic-usage#start-gesture)o un gesto de [eclosión](hololens1-basic-usage.md) en HoloLens (1era generación).</span><span class="sxs-lookup"><span data-stu-id="3596f-148">To open the [**Start** menu](holographic-home.md), perform a [Start gesture](https://docs.microsoft.com/hololens/hololens2-basic-usage#start-gesture) or [bloom](hololens1-basic-usage.md) gesture on HoloLens (1st gen).</span></span>
1. <span data-ttu-id="3596f-149">Seleccione la aplicación de la tienda.</span><span class="sxs-lookup"><span data-stu-id="3596f-149">Select the Store app.</span></span>
1. <span data-ttu-id="3596f-150">Mire la parte superior derecha de la aplicación de la Tienda.</span><span class="sxs-lookup"><span data-stu-id="3596f-150">Look to the top right of the Store app.</span></span> 
1. <span data-ttu-id="3596f-151">Seleccione el botón **"..."** o "Ver más".</span><span class="sxs-lookup"><span data-stu-id="3596f-151">Select the **"..."** or “See more” button.</span></span>

   > [!div class="mx-imgBorder"]
   > ![Captura de pantalla de la aplicación Microsoft Store.](images/store-update-1.png)

1. <span data-ttu-id="3596f-153">Seleccione **Descargas y actualizaciones**.</span><span class="sxs-lookup"><span data-stu-id="3596f-153">Select **Downloads and updates**.</span></span>
    1. <span data-ttu-id="3596f-154">Si el dispositivo ha identificado previamente actualizaciones, es posible que vea una flecha hacia abajo y un número, lo que representa las actualizaciones pendientes.</span><span class="sxs-lookup"><span data-stu-id="3596f-154">If your device has previously identified updates you may see a down arrow and a number, this represents pending updates.</span></span>
1. <span data-ttu-id="3596f-155">Seleccione **Obtener actualizaciones**.</span><span class="sxs-lookup"><span data-stu-id="3596f-155">Select **Get updates**.</span></span> <span data-ttu-id="3596f-156">El dispositivo ahora buscará actualizaciones y las configurará para descargar e instalar.</span><span class="sxs-lookup"><span data-stu-id="3596f-156">Your device will now search for updates and set them to download and install.</span></span> 
 
   > [!div class="mx-imgBorder"]
   > ![Captura de pantalla de cómo obtener actualizaciones de la aplicación de Microsoft Store.](images/store-update-2.png.jpg)

> [!NOTE]
> <span data-ttu-id="3596f-158">Si las aplicaciones de su dispositivo fueron interrumpidas por su organización, podrán actualizarse a través de los mismos métodos de administración de aplicaciones comerciales.</span><span class="sxs-lookup"><span data-stu-id="3596f-158">If the apps on your device were distrubted by your organization they can be updated through the same commercial app management methods.</span></span> <span data-ttu-id="3596f-159">Si esto aplica a su situación, obtenga más información en nuestra [introducción a la implementación de aplicaciones comerciales.](app-deploy-overview.md)</span><span class="sxs-lookup"><span data-stu-id="3596f-159">If this applies to your situation, read more via our [overview of commercial app deployment.](app-deploy-overview.md)</span></span>
>
> <span data-ttu-id="3596f-160">Si desea actualizar una aplicación personalizada que se ha instalado de prueba o implementado, tendrá que usar el mismo método con la versión actualizada de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3596f-160">If you would like to update a custom app that has been sideloaded or deployed, you will need to use the same method with the updated version of your app.</span></span> <span data-ttu-id="3596f-161">Para obtener más información sobre la instalación y ejecución de aplicaciones personalizadas, lea [aplicaciones holográficas personalizadas](holographic-custom-apps.md).</span><span class="sxs-lookup"><span data-stu-id="3596f-161">To learn more about installing and running custom apps, read [custom holographic applications](holographic-custom-apps.md).</span></span>

## <span data-ttu-id="3596f-162">Desinstalar aplicaciones</span><span class="sxs-lookup"><span data-stu-id="3596f-162">Uninstall apps</span></span>

<span data-ttu-id="3596f-163">Hay dos formas de desinstalar aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="3596f-163">There are two ways to uninstall applications.</span></span>  <span data-ttu-id="3596f-164">Puede desinstalar aplicaciones a través de Microsoft Store o del menú Inicio.</span><span class="sxs-lookup"><span data-stu-id="3596f-164">You can uninstall applications through the Microsoft Store or Start menu.</span></span>

### <span data-ttu-id="3596f-165">Desinstalar desde el menú de inicio</span><span class="sxs-lookup"><span data-stu-id="3596f-165">Uninstall from the Start menu</span></span>

<span data-ttu-id="3596f-166">En el menú de **Inicio** o en la lista de **Todas las aplicaciones**, busque la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3596f-166">On the **Start** menu or in the **All apps** list, browse to the app.</span></span> <span data-ttu-id="3596f-167">Seleccione y mantenga pulsado hasta que aparezca el menú, luego seleccione **Desinstalar**.</span><span class="sxs-lookup"><span data-stu-id="3596f-167">Select and hold until the menu appears, then select **Uninstall**.</span></span>

### <span data-ttu-id="3596f-168">Desinstalar desde Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="3596f-168">Uninstall from the Microsoft Store</span></span>

<span data-ttu-id="3596f-169">Abra el Microsoft Store desde el menú **Inicio**, y luego busque la aplicación que desea desinstalar.</span><span class="sxs-lookup"><span data-stu-id="3596f-169">Open the Microsoft Store from the **Start** menu, and then browse for the application you'd like to uninstall.</span></span>  <span data-ttu-id="3596f-170">En la página de la tienda, cada aplicación que ha instalado tiene un botón para**Desinstalar**.</span><span class="sxs-lookup"><span data-stu-id="3596f-170">On the Store page, each application that you have installed has an **Uninstall** button.</span></span>
