---
title: Mapa de espacios físicos con HoloLens
description: HoloLens aprende lo que luce un espacio a lo largo del tiempo. Los usuarios pueden facilitar este proceso moviendo la HoloLens en ciertos modos a través del espacio.
ms.assetid: bd55ecd1-697a-4b09-8274-48d1499fcb0b
author: dorreneb
ms.author: dobrown
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.date: 09/16/2019
keywords: hololens, Windows Mixed Reality, diseño, asignación espacial, HoloLens, reconstrucción superficial, malla, control de cabezal, asignación
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 1 (1st gen)
- HoloLens 2
ms.openlocfilehash: 992b17160eb6ba6ca2f6c8b12e112b98ab154774
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2020
ms.locfileid: "10829026"
---
# <span data-ttu-id="293e9-105">Mapa de espacios físicos con HoloLens</span><span class="sxs-lookup"><span data-stu-id="293e9-105">Map physical spaces with HoloLens</span></span>

<span data-ttu-id="293e9-106">HoloLens funde un holograma con su mundo físico.</span><span class="sxs-lookup"><span data-stu-id="293e9-106">HoloLens blends holograms with your physical world.</span></span> <span data-ttu-id="293e9-107">Para hacerlo, HoloLens tiene que obtener información sobre el mundo físico de su sitio web y recordar en qué lugar del espacio se colocan hologramas.</span><span class="sxs-lookup"><span data-stu-id="293e9-107">To do that, HoloLens has to learn about the physical world around you and remember where you place holograms within that space.</span></span>

<span data-ttu-id="293e9-108">Con el tiempo, HoloLens crea un *mapa espacial* del entorno que ha visto.</span><span class="sxs-lookup"><span data-stu-id="293e9-108">Over time, the HoloLens builds up a *spatial map* of the environment that it has seen.</span></span>  <span data-ttu-id="293e9-109">HoloLens actualiza el mapa a medida que el entorno cambia.</span><span class="sxs-lookup"><span data-stu-id="293e9-109">HoloLens updates the map as the environment changes.</span></span> <span data-ttu-id="293e9-110">Siempre y cuando haya iniciado sesión y el dispositivo esté activado, HoloLens crea y actualiza sus mapas espaciales.</span><span class="sxs-lookup"><span data-stu-id="293e9-110">As long as you are logged in and the device is turned on, HoloLens creates and updates your spatial maps.</span></span> <span data-ttu-id="293e9-111">Si mantiene o se lleva el dispositivo con las cámaras a las que señala un espacio, HoloLens intenta asignar el área.</span><span class="sxs-lookup"><span data-stu-id="293e9-111">If you hold or wear the device with the cameras pointed at a space, the HoloLens tries to map the area.</span></span> <span data-ttu-id="293e9-112">Mientras HoloLens aprende un espacio de forma natural a lo largo del tiempo, hay varias maneras en las que HoloLens le ayuda a la hora de diseñar su espacio de manera más rápida y eficaz.</span><span class="sxs-lookup"><span data-stu-id="293e9-112">While the HoloLens learns a space naturally over time, there are ways in which you can help HoloLens map your space more quickly and efficiently.</span></span>  

> [!NOTE]
> <span data-ttu-id="293e9-113">Si su HoloLens no puede mapear su espacio o está fuera de calibración, el HoloLens puede entrar en modo limitado.</span><span class="sxs-lookup"><span data-stu-id="293e9-113">If your HoloLens can't map your space or is out of calibration, HoloLens may enter Limited mode.</span></span> <span data-ttu-id="293e9-114">En el modo limitado, no podrá colocar hologramas en su entorno.</span><span class="sxs-lookup"><span data-stu-id="293e9-114">In Limited mode, you won't be able to place holograms in your surroundings.</span></span>

<span data-ttu-id="293e9-115">Este artículo explica cómo HoloLens asigna espacios, cómo mejorar la asignación espacial y cómo administrar los datos espaciales que recopila.</span><span class="sxs-lookup"><span data-stu-id="293e9-115">This article explains how HoloLens maps spaces, how to improve spatial mapping, and how to manage the spatial data that HoloLens collects.</span></span>

## <span data-ttu-id="293e9-116">Elección y configuración de su espacio</span><span class="sxs-lookup"><span data-stu-id="293e9-116">Choosing and setting up and your space</span></span>

<span data-ttu-id="293e9-117">Las características de su entorno pueden dificultar que HoloLens interprete un espacio.</span><span class="sxs-lookup"><span data-stu-id="293e9-117">Features in your environment can make it difficult for the HoloLens to interpret a space.</span></span> <span data-ttu-id="293e9-118">Los niveles de luz, los materiales en el espacio, el diseño de los objetos y otros pueden afectar a la forma en que HoloLens asigna un área.</span><span class="sxs-lookup"><span data-stu-id="293e9-118">Light levels, materials in the space, the layout of objects, and more can all affect how HoloLens maps an area.</span></span>

<span data-ttu-id="293e9-119">HoloLens funciona mejor en ciertos tipos de entornos.</span><span class="sxs-lookup"><span data-stu-id="293e9-119">HoloLens works best in certain kinds of environments.</span></span> <span data-ttu-id="293e9-120">Para crear el mejor mapa de espacios espaciales, elija una sala que tenga la luz adecuada y disponga de suficiente espacio.</span><span class="sxs-lookup"><span data-stu-id="293e9-120">To produce the best spatial map, choose a room that has adequate light and plenty of space.</span></span> <span data-ttu-id="293e9-121">Evite espacios en blanco y negro en oscuro que contengan una gran cantidad de superficie oscura, brillante o traslúcida (por ejemplo, espejos o cortinas gauzy).</span><span class="sxs-lookup"><span data-stu-id="293e9-121">Avoid dark spaces and rooms that have a lot of dark, shiny, or translucent surfaces (for instance, mirrors or gauzy curtains).</span></span>

<span data-ttu-id="293e9-122">HoloLens está optimizado para el uso en interiores.</span><span class="sxs-lookup"><span data-stu-id="293e9-122">HoloLens is optimized for indoor use.</span></span> <span data-ttu-id="293e9-123">La asignación espacial también funciona mejor cuando se enciende Wi-Fi, aunque no es necesario conectarse a una red.</span><span class="sxs-lookup"><span data-stu-id="293e9-123">Spatial mapping also works best when Wi-Fi is turned on, although it doesn't have to be connected to a network.</span></span> <span data-ttu-id="293e9-124">HoloLens puede obtener puntos de acceso Wi-Fi incluso si no está conectado o autenticado.</span><span class="sxs-lookup"><span data-stu-id="293e9-124">HoloLens can obtain Wi-Fi access points even if it is not connected or authenticated.</span></span> <span data-ttu-id="293e9-125">La funcionalidad de HoloLens no cambia si los puntos de acceso se conectan a través de Internet o de forma local o intranet.</span><span class="sxs-lookup"><span data-stu-id="293e9-125">HoloLens functionality does not change whether the access points are internet-connected or intranet/local only.</span></span>

<span data-ttu-id="293e9-126">Solo use HoloLens en lugares seguros sin peligro.</span><span class="sxs-lookup"><span data-stu-id="293e9-126">Only use HoloLens in safe places with no tripping hazards.</span></span> <span data-ttu-id="293e9-127">[Más sobre la seguridad](https://support.microsoft.com/help/4023454/safety-information).</span><span class="sxs-lookup"><span data-stu-id="293e9-127">[More on safety](https://support.microsoft.com/help/4023454/safety-information).</span></span>

## <span data-ttu-id="293e9-128">Asignación de espacio</span><span class="sxs-lookup"><span data-stu-id="293e9-128">Mapping your space</span></span>

<span data-ttu-id="293e9-129">Ya está listo para empezar a asignar el spare.</span><span class="sxs-lookup"><span data-stu-id="293e9-129">Now you're ready to start mapping your spare.</span></span>  <span data-ttu-id="293e9-130">Cuando HoloLens inicia la asignación de un entorno, verá un gráfico de la malla que se propaga por el espacio.</span><span class="sxs-lookup"><span data-stu-id="293e9-130">When HoloLens starts mapping your surroundings, you'll see a mesh graphic spreading over the space.</span></span>  <span data-ttu-id="293e9-131">En la página principal de la realidad mixta, puede activar el mapa que se muestra al seleccionar en una superficie asignada.</span><span class="sxs-lookup"><span data-stu-id="293e9-131">In mixed reality home, you can trigger the map to show by selecting on a mapped surface.</span></span>

<span data-ttu-id="293e9-132">Aquí encontrará directrices para crear un magnífico mapa espacial.</span><span class="sxs-lookup"><span data-stu-id="293e9-132">Here are guidelines for building a great spatial map.</span></span>

### <span data-ttu-id="293e9-133">Entender los escenarios para el área</span><span class="sxs-lookup"><span data-stu-id="293e9-133">Understand the scenarios for the area</span></span>

<span data-ttu-id="293e9-134">Es importante gastar el tiempo necesario para usar HoloLens, por lo que la equivalencia es relevante y completa.</span><span class="sxs-lookup"><span data-stu-id="293e9-134">It is important to spend the most time where you will be using the HoloLens, so that the map is relevant and complete.</span></span> <span data-ttu-id="293e9-135">Por ejemplo, si un escenario de usuario para HoloLens implica moverse de un punto a otro en el punto B, desplácese por la ruta de dos a tres ocasiones y busque en todas las direcciones a medida que se desplace.</span><span class="sxs-lookup"><span data-stu-id="293e9-135">For example, if a user scenario for HoloLens involves moving from Point A to Point B, walk that path two to three times, looking in all directions as you move.</span></span>  

### <span data-ttu-id="293e9-136">Recorra lentamente alrededor del espacio</span><span class="sxs-lookup"><span data-stu-id="293e9-136">Walk slowly around the space</span></span>

<span data-ttu-id="293e9-137">Si se dirige demasiado rápido en torno al área, es probable que HoloLens se quede con errores de asignación de áreas.</span><span class="sxs-lookup"><span data-stu-id="293e9-137">If you walk too quickly around the area, it's likely that the HoloLens will miss mapping areas.</span></span> <span data-ttu-id="293e9-138">Recorra lentamente alrededor del espacio y, a continuación, detenga cada 5 a 8 pies para buscar en todo el entorno.</span><span class="sxs-lookup"><span data-stu-id="293e9-138">Walk slowly around the space, stopping every 5-8 feet to look around at your surroundings.</span></span>  

<span data-ttu-id="293e9-139">Los movimientos suaves también ayudan a la asignación de HoloLens de forma más eficaz.</span><span class="sxs-lookup"><span data-stu-id="293e9-139">Smooth movements also help the HoloLens map more efficiently.</span></span>

### <span data-ttu-id="293e9-140">Buscar en todas las direcciones</span><span class="sxs-lookup"><span data-stu-id="293e9-140">Look in all directions</span></span>

<span data-ttu-id="293e9-141">La búsqueda a medida que se asigna el espacio les proporciona más información sobre los puntos que están relacionados entre sí.</span><span class="sxs-lookup"><span data-stu-id="293e9-141">Looking around as you map the space gives the HoloLens more data on where points are relative to each other.</span></span>  

<span data-ttu-id="293e9-142">Si no lo hace, es posible que HoloLens no pueda averiguar el lugar en el que se encuentra el techo en la habitación.</span><span class="sxs-lookup"><span data-stu-id="293e9-142">If you don't look up, for example, the HoloLens may not know where the ceiling in a room is.</span></span>  

<span data-ttu-id="293e9-143">No olvide tener que buscar en el piso cuando asigne el espacio.</span><span class="sxs-lookup"><span data-stu-id="293e9-143">Don't forget to look down at the floor as you map the space.</span></span>

### <span data-ttu-id="293e9-144">Cubrir las áreas clave varias veces</span><span class="sxs-lookup"><span data-stu-id="293e9-144">Cover key areas multiple times</span></span>

<span data-ttu-id="293e9-145">Desplazarse por un área varias veces ayudará a recoger las características que es posible que falten en el primer tutorial.</span><span class="sxs-lookup"><span data-stu-id="293e9-145">Moving through an area multiple times will help pick up features you may have missed on the first walkthrough.</span></span> <span data-ttu-id="293e9-146">Para crear un mapa ideal, pruebe a resaltar un área de dos a tres veces.</span><span class="sxs-lookup"><span data-stu-id="293e9-146">To build an ideal map, try traversing an area two to three times.</span></span>

<span data-ttu-id="293e9-147">Si es posible, al repetir estos movimientos, pase el tiempo pasando por un área en una dirección y, después, vuelva a la parte posterior y, a continuación, vuelva a desplazarse a la forma en que llegó.</span><span class="sxs-lookup"><span data-stu-id="293e9-147">If possible, while repeating these movements, spend time walking through an area in one direction, then turn around and walk back the way you came.</span></span>

### <span data-ttu-id="293e9-148">Llevar la hora asignada al área</span><span class="sxs-lookup"><span data-stu-id="293e9-148">Take your time mapping the area</span></span>

<span data-ttu-id="293e9-149">Puede tardar entre 15 y 20 minutos en que HoloLens se asigne completamente y se ajuste a su entorno.</span><span class="sxs-lookup"><span data-stu-id="293e9-149">It can take between 15 and 20 minutes for the HoloLens to fully map and adjust itself to its surroundings.</span></span> <span data-ttu-id="293e9-150">Si tiene un espacio en el que tiene previsto usar HoloLens con frecuencia, al dedicar ese tiempo al espacio para asignar el espacio, se pueden evitar los problemas más adelante.</span><span class="sxs-lookup"><span data-stu-id="293e9-150">If you have a space in which you plan to use a HoloLens frequently, taking that time up front to map the space can prevent issues later on.</span></span>  

## <span data-ttu-id="293e9-151">Posibles errores en el mapa espacial</span><span class="sxs-lookup"><span data-stu-id="293e9-151">Possible errors in the spatial map</span></span>

<span data-ttu-id="293e9-152">Los errores en los datos de asignación espacial se dividen en algunas categorías:</span><span class="sxs-lookup"><span data-stu-id="293e9-152">Errors in spatial mapping data fall into a few categories:</span></span>

- <span data-ttu-id="293e9-153">*Orificios*: no se muestran las superficies del mundo real en los datos de la asignación espacial.</span><span class="sxs-lookup"><span data-stu-id="293e9-153">*Holes*: Real-world surfaces are missing from the spatial mapping data.</span></span>
- <span data-ttu-id="293e9-154">*Hallucinations*: existen superficies en los datos de asignación espacial que no existen en el mundo real.</span><span class="sxs-lookup"><span data-stu-id="293e9-154">*Hallucinations*: Surfaces exist in the spatial mapping data that do not exist in the real world.</span></span>
- <span data-ttu-id="293e9-155">*Túneles espaciales*: HoloLens "pierde" parte del mapa espacial pensando en que se encuentra en otra parte del mapa que realmente es.</span><span class="sxs-lookup"><span data-stu-id="293e9-155">*Wormholes*: HoloLens 'loses' part of the spatial map by thinking it is in a different part of the map than it actually is.</span></span>
- <span data-ttu-id="293e9-156">*Bias*: las superficies en los datos de la asignación espacial se alinean de forma imperfecta con las superficies del mundo real, ya sea insertadas o extraídas.</span><span class="sxs-lookup"><span data-stu-id="293e9-156">*Bias*: Surfaces in the spatial mapping data are imperfectly aligned with real-world surfaces, either pushed in or pulled out.</span></span>

<span data-ttu-id="293e9-157">Si ve alguno de estos errores, utilice el [FeedbackHub](hololens-feedback.md) para enviar comentarios.</span><span class="sxs-lookup"><span data-stu-id="293e9-157">If you see any of these errors please use the [FeedbackHub](hololens-feedback.md) to send feedback.</span></span>

## <span data-ttu-id="293e9-158">Seguridad y almacenamiento para datos espaciales</span><span class="sxs-lookup"><span data-stu-id="293e9-158">Security and storage for spatial data</span></span>

<span data-ttu-id="293e9-159">La actualización de la versión 1803 de Windows 10 para Microsoft HoloLens y posterior almacena datos de asignación en una base de datos local (en el dispositivo).</span><span class="sxs-lookup"><span data-stu-id="293e9-159">Windows 10 version 1803 update for Microsoft HoloLens and later stores mapping data in a local (on-device) database.</span></span>

<span data-ttu-id="293e9-160">Los usuarios de HoloLens no pueden acceder a la base de datos de mapas directamente, incluso si el dispositivo está conectado a un equipo PC o al usar la aplicación del explorador de archivos.</span><span class="sxs-lookup"><span data-stu-id="293e9-160">HoloLens users cannot directly access the map database, even when the device is plugged into a PC or when using the File Explorer app.</span></span> <span data-ttu-id="293e9-161">Cuando se habilita BitLocker en HoloLens, los datos de mapa almacenados también se cifran junto con todo el volumen.</span><span class="sxs-lookup"><span data-stu-id="293e9-161">When BitLocker is enabled on HoloLens, the stored map data is also encrypted along with the entire volume.</span></span>

### <span data-ttu-id="293e9-162">Quitar los datos de mapa y los espacios conocidos de HoloLens</span><span class="sxs-lookup"><span data-stu-id="293e9-162">Remove map data and known spaces from HoloLens</span></span>

<span data-ttu-id="293e9-163">Hay dos opciones para eliminar datos de mapa en la **Configuración> > hologramas del sistema**:</span><span class="sxs-lookup"><span data-stu-id="293e9-163">There are two options for deleting map data in **Settings > System > Holograms**:</span></span>

- <span data-ttu-id="293e9-164">Para eliminar el holograma cerca, seleccione **Quitar hologramas próximos**.</span><span class="sxs-lookup"><span data-stu-id="293e9-164">To delete nearby holograms, select **Remove nearby holograms**.</span></span> <span data-ttu-id="293e9-165">Este comando borra los datos de mapa y los hologramas anclados del espacio actual.</span><span class="sxs-lookup"><span data-stu-id="293e9-165">This command clears the map data and anchored holograms for the current space.</span></span> <span data-ttu-id="293e9-166">Si continúa utilizando el dispositivo en el mismo espacio, se crea y se almacena una sección de mapa completamente nuevo para reemplazar la información eliminada.</span><span class="sxs-lookup"><span data-stu-id="293e9-166">If you continue to use the device in the same space, it creates and stores a brand new map section to replace the deleted information.</span></span>

   > [!NOTE]
   > <span data-ttu-id="293e9-167">Los hologramas "Cercanos" son hologramas que están anclados en la misma sección de mapa en el espacio actual.</span><span class="sxs-lookup"><span data-stu-id="293e9-167">"Nearby" holograms are holograms that are anchored within the same map section in the current space.</span></span>

   <span data-ttu-id="293e9-168">Por ejemplo, puede usar esta opción para borrar los datos de mapa relacionados con el trabajo sin afectar a los datos de mapa relacionados con el hogar.</span><span class="sxs-lookup"><span data-stu-id="293e9-168">For example, you can use this option to clear work-related map data without affecting any home-related map data.</span></span>

- <span data-ttu-id="293e9-169">Para eliminar todos los hologramas, seleccione **Quitar todos los hologramas**.</span><span class="sxs-lookup"><span data-stu-id="293e9-169">To delete all holograms, select **Remove all holograms**.</span></span> <span data-ttu-id="293e9-170">Este comando borra todos los datos de mapa almacenados en el dispositivo, así como todos los hologramas delimitados.</span><span class="sxs-lookup"><span data-stu-id="293e9-170">This command clears all map data that is stored on the device as well as all anchored holograms.</span></span> <span data-ttu-id="293e9-171">Tendrá que realizar explícitamente un holograma.</span><span class="sxs-lookup"><span data-stu-id="293e9-171">You will need to explicitly place any holograms.</span></span> <span data-ttu-id="293e9-172">No podrá volver a detectar los hologramas que colocó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="293e9-172">You will not be able to rediscover the previously-placed holograms.</span></span>

> [!NOTE]
> <span data-ttu-id="293e9-173">Después de quitar los hologramas o cercanos, HoloLens inicia inmediatamente el examen y la asignación del espacio actual.</span><span class="sxs-lookup"><span data-stu-id="293e9-173">After you remove nearby or all holograms, HoloLens immediately starts scanning and mapping the current space.</span></span>

### <span data-ttu-id="293e9-174">Datos de redes Wi-Fi en mapas espaciales</span><span class="sxs-lookup"><span data-stu-id="293e9-174">Wi-Fi data in spatial maps</span></span>

<span data-ttu-id="293e9-175">HoloLens almacena características Wi-Fi para ayudarle a correlacionar las ubicaciones de hologramas y las secciones de mapa que se almacenan en la base de datos HoloLens de espacios conocidos.</span><span class="sxs-lookup"><span data-stu-id="293e9-175">HoloLens stores Wi-Fi characteristics to help correlate hologram locations and map sections that are stored within the HoloLens database of known spaces.</span></span> <span data-ttu-id="293e9-176">La información sobre las características de Wi-Fi no es accesible para los usuarios y no se envía a Microsoft a través de la nube o mediante telemetría.</span><span class="sxs-lookup"><span data-stu-id="293e9-176">Information about Wi-Fi characteristics is not accessible to users, and not sent to Microsoft using the cloud or using telemetry.</span></span>

<span data-ttu-id="293e9-177">Siempre y cuando se habilite Wi-Fi, HoloLens correlaciona los datos de mapa con puntos de acceso Wi-Fi cercanos.</span><span class="sxs-lookup"><span data-stu-id="293e9-177">As long as Wi-Fi is enabled, HoloLens correlates map data with nearby Wi-Fi access points.</span></span> <span data-ttu-id="293e9-178">No hay ninguna diferencia en el comportamiento tanto si una red está conectada como si solo se detecta cerca.</span><span class="sxs-lookup"><span data-stu-id="293e9-178">There is no difference in behavior whether a network is connected or just detected nearby.</span></span> <span data-ttu-id="293e9-179">Si Wi-Fi está deshabilitado, HoloLens continúa buscando en el espacio.</span><span class="sxs-lookup"><span data-stu-id="293e9-179">If Wi-Fi is disabled, HoloLens still searches the space.</span></span> <span data-ttu-id="293e9-180">Sin embargo, HoloLens tiene que buscar más datos de mapas en la base de datos Spaces y es posible que necesite más tiempo para encontrar hologramas.</span><span class="sxs-lookup"><span data-stu-id="293e9-180">However, HoloLens has to search more of the map data within the spaces database, and may need more time to find holograms.</span></span> <span data-ttu-id="293e9-181">En ausencia de la información de Wi-Fi, HoloLens tiene que comparar las exploraciones activas con todos los anclajes de hologramas y las secciones de mapa que se almacenan en el dispositivo para localizar la parte correcta del mapa.</span><span class="sxs-lookup"><span data-stu-id="293e9-181">Without the Wi-Fi info, the HoloLens has to compare active scans to all hologram anchors and map sections that are stored on the device in order to locate the correct portion of the map.</span></span>

## <span data-ttu-id="293e9-182">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="293e9-182">Related topics</span></span>

- [<span data-ttu-id="293e9-183">Diseño de mapas espaciales</span><span class="sxs-lookup"><span data-stu-id="293e9-183">Spatial mapping design</span></span>](https://docs.microsoft.com/windows/mixed-reality/spatial-mapping-design)
