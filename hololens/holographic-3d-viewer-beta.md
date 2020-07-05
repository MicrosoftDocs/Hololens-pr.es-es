---
title: Usar el visor 3D en HoloLens (1.ª generación)
description: Describa los tipos de archivos y características que admite 3D Viewer en HoloLens (1ª generación), y cómo utilizar y solucionar los problemas de la aplicación.
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.localizationpriority: high
ms.date: 10/30/2019
ms.reviewer: scooley
audience: ITPro
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 47fe1fd5dc164c56ce22a09d7edf5bffdb60ea14
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828886"
---
# <span data-ttu-id="a4e1f-103">Usar el visor 3D en HoloLens (1.ª generación)</span><span class="sxs-lookup"><span data-stu-id="a4e1f-103">Using 3D Viewer on HoloLens (1st gen)</span></span>

<span data-ttu-id="a4e1f-104">El visor 3D le permite ver modelos 3D en HoloLens (1ª gen.).</span><span class="sxs-lookup"><span data-stu-id="a4e1f-104">3D Viewer lets you view 3D models on HoloLens (1st gen).</span></span> <span data-ttu-id="a4e1f-105">Puede abrir y ver *compatibles*. FBX los archivos de Microsoft Edge, OneDrive y otras aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-105">You can open and view *supported* .fbx files from Microsoft Edge, OneDrive, and other apps.</span></span>

>[!NOTE]
><span data-ttu-id="a4e1f-106">Este artículo se aplica a la aplicación de**Visor 3D**de Unity envolvente, que es compatible con archivos. FBX y solo está disponible en HoloLens (1ª gen.).</span><span class="sxs-lookup"><span data-stu-id="a4e1f-106">This article applies to the immersive Unity **3D Viewer** app, which supports .fbx files and is only available on HoloLens (1st gen).</span></span> <span data-ttu-id="a4e1f-107">La aplicación preinstalada**del visor de 3D** en HoloLens 2 es compatible con la apertura de modelos personalizados. glb 3D en la realidad en la página de inicio (vea [información general sobre los requisitos de activos](https://docs.microsoft.com/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-107">The pre-installed **3D Viewer** app on HoloLens 2 supports opening custom .glb 3D models in the mixed reality home (see [Asset requirements overview](https://docs.microsoft.com/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview) for more details.</span></span>

<span data-ttu-id="a4e1f-108">Si tiene problemas para abrir un modelo 3D en el visor 3D, o si algunas de las características de su modelo 3D no son compatibles, vea [especificaciones de contenido compatible](#supported-content-specifications).</span><span class="sxs-lookup"><span data-stu-id="a4e1f-108">If you're having trouble opening a 3D model in 3D Viewer, or certain features of your 3D model are unsupported, see [Supported content specifications](#supported-content-specifications).</span></span>

<span data-ttu-id="a4e1f-109">Para crear u optimizar modelos 3D para usarlos con el visor 3D, vea [optimizar modelos 3D para el visor 3D](#optimizing-3d-models-for-3d-viewer).</span><span class="sxs-lookup"><span data-stu-id="a4e1f-109">To build or optimize 3D models for use with 3D Viewer, see [Optimizing 3D models for 3D Viewer](#optimizing-3d-models-for-3d-viewer).</span></span>

<span data-ttu-id="a4e1f-110">Hay dos formas de abrir un modelo 3D en HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-110">There are two ways to open a 3D model on HoloLens.</span></span> <span data-ttu-id="a4e1f-111">Para obtener más información, vea [Ver los archivos FBX en HoloLens](#viewing-fbx-files-on-hololens).</span><span class="sxs-lookup"><span data-stu-id="a4e1f-111">See [Viewing FBX files on HoloLens](#viewing-fbx-files-on-hololens) to learn more.</span></span>

<span data-ttu-id="a4e1f-112">Si tiene problemas después de leer estos temas, vea [Solución de problemas](#troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="a4e1f-112">If you're having trouble after reading these topics, see [Troubleshooting](#troubleshooting).</span></span>

## <span data-ttu-id="a4e1f-113">Especificaciones de contenido compatibles</span><span class="sxs-lookup"><span data-stu-id="a4e1f-113">Supported content specifications</span></span>

### <span data-ttu-id="a4e1f-114">Formato de archivo</span><span class="sxs-lookup"><span data-stu-id="a4e1f-114">File format</span></span>

- <span data-ttu-id="a4e1f-115">Formato FBX</span><span class="sxs-lookup"><span data-stu-id="a4e1f-115">FBX format</span></span>
- <span data-ttu-id="a4e1f-116">Versión máxima de FBX 2015.1.0</span><span class="sxs-lookup"><span data-stu-id="a4e1f-116">Maximum FBX release 2015.1.0</span></span>

### <span data-ttu-id="a4e1f-117">Tamaño de archivo</span><span class="sxs-lookup"><span data-stu-id="a4e1f-117">File size</span></span>

- <span data-ttu-id="a4e1f-118">Mínimo 5 GB</span><span class="sxs-lookup"><span data-stu-id="a4e1f-118">Minimum 5 KB</span></span>
- <span data-ttu-id="a4e1f-119">Máximo 500 MB</span><span class="sxs-lookup"><span data-stu-id="a4e1f-119">Maximum 500 MB</span></span>

### <span data-ttu-id="a4e1f-120">Geometría</span><span class="sxs-lookup"><span data-stu-id="a4e1f-120">Geometry</span></span>

- <span data-ttu-id="a4e1f-121">Solo modelos poligonales.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-121">Polygonal models only.</span></span> <span data-ttu-id="a4e1f-122">Ninguna superficie de subdivisión o NURBs</span><span class="sxs-lookup"><span data-stu-id="a4e1f-122">No subdivision surfaces or NURBs</span></span>
- <span data-ttu-id="a4e1f-123">Sistema de coordenadas izquierda</span><span class="sxs-lookup"><span data-stu-id="a4e1f-123">Right-handed coordinate system</span></span>
- <span data-ttu-id="a4e1f-124">No se admite la distorsión en matrices de transformación.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-124">Shear in transformation matrices is not supported</span></span>

### <span data-ttu-id="a4e1f-125">Texturas</span><span class="sxs-lookup"><span data-stu-id="a4e1f-125">Textures</span></span>

- <span data-ttu-id="a4e1f-126">Los mapas de textura deben estar incrustados en el archivo FBX</span><span class="sxs-lookup"><span data-stu-id="a4e1f-126">Texture maps must be embedded in the FBX file</span></span>
- <span data-ttu-id="a4e1f-127">Formatos de imagen admitidos</span><span class="sxs-lookup"><span data-stu-id="a4e1f-127">Supported image formats</span></span>
  - <span data-ttu-id="a4e1f-128">Imágenes JPEG y PNG</span><span class="sxs-lookup"><span data-stu-id="a4e1f-128">JPEG and PNG images</span></span>
  - <span data-ttu-id="a4e1f-129">Imágenes BMP (color verdadero, RGB de 24 bits)</span><span class="sxs-lookup"><span data-stu-id="a4e1f-129">BMP images (24-bit RGB true-color)</span></span>
  - <span data-ttu-id="a4e1f-130">Imágenes TGA (RVA de 24 bits y 32 bits de RGBQ en color verdadero)</span><span class="sxs-lookup"><span data-stu-id="a4e1f-130">TGA images (24-bit RGB and 32-bit RGBQ true-color)</span></span>
- <span data-ttu-id="a4e1f-131">Resolución máxima de textura de 2048x2048</span><span class="sxs-lookup"><span data-stu-id="a4e1f-131">Maximum texture resolution of 2048x2048</span></span>
- <span data-ttu-id="a4e1f-132">Un máximo de un mapa de difusión, un mapa normal y un mapa de cubos de reflexión por malla</span><span class="sxs-lookup"><span data-stu-id="a4e1f-132">Maximum of one diffuse map, one normal map, and one reflection cube map per mesh</span></span>
- <span data-ttu-id="a4e1f-133">El canal alfa en texturas difusas hace que los píxeles se descartan si se muestra debajo 50%</span><span class="sxs-lookup"><span data-stu-id="a4e1f-133">Alpha channel in diffuse textures causes pixels to be discarded if below 50%</span></span>

### <span data-ttu-id="a4e1f-134">Animación</span><span class="sxs-lookup"><span data-stu-id="a4e1f-134">Animation</span></span>

- <span data-ttu-id="a4e1f-135">Animación de escalar/rotar/traslación en objetos individuales</span><span class="sxs-lookup"><span data-stu-id="a4e1f-135">Scale/rotation/translation animation on individual objects</span></span>
- <span data-ttu-id="a4e1f-136">Animación esquemática (RIGGED) con la piel</span><span class="sxs-lookup"><span data-stu-id="a4e1f-136">Skeletal (rigged) animation with skinning</span></span>
  - <span data-ttu-id="a4e1f-137">Máximo de 4 influencias por vértice</span><span class="sxs-lookup"><span data-stu-id="a4e1f-137">Maximum of 4 influences per vertex</span></span>

### <span data-ttu-id="a4e1f-138">Materiales</span><span class="sxs-lookup"><span data-stu-id="a4e1f-138">Materials</span></span>

- <span data-ttu-id="a4e1f-139">Se admiten materiales Lambert y Phong con parámetros ajustables.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-139">Lambert and Phong materials are supported, with adjustable parameters</span></span>
- <span data-ttu-id="a4e1f-140">Propiedades de material compatible con Lambert</span><span class="sxs-lookup"><span data-stu-id="a4e1f-140">Supported material properties for Lambert</span></span>
  - <span data-ttu-id="a4e1f-141">Textura principal (prueba RGB + Alpha)</span><span class="sxs-lookup"><span data-stu-id="a4e1f-141">Main Texture (RGB + Alpha Test)</span></span>
  - <span data-ttu-id="a4e1f-142">Color difuso (RGB)</span><span class="sxs-lookup"><span data-stu-id="a4e1f-142">Diffuse Color (RGB)</span></span>
  - <span data-ttu-id="a4e1f-143">Color ambiente (RGB)</span><span class="sxs-lookup"><span data-stu-id="a4e1f-143">Ambient Color (RGB)</span></span>
- <span data-ttu-id="a4e1f-144">Propiedades de material admitidas para Phong</span><span class="sxs-lookup"><span data-stu-id="a4e1f-144">Supported material properties for Phong</span></span>
  - <span data-ttu-id="a4e1f-145">Textura principal (prueba RGB + Alpha)</span><span class="sxs-lookup"><span data-stu-id="a4e1f-145">Main Texture (RGB + Alpha Test)</span></span>
  - <span data-ttu-id="a4e1f-146">Color difuso (RGB)</span><span class="sxs-lookup"><span data-stu-id="a4e1f-146">Diffuse Color (RGB)</span></span>
  - <span data-ttu-id="a4e1f-147">Color ambiente (RGB)</span><span class="sxs-lookup"><span data-stu-id="a4e1f-147">Ambient Color (RGB)</span></span>
  - <span data-ttu-id="a4e1f-148">Color especular (RGB)</span><span class="sxs-lookup"><span data-stu-id="a4e1f-148">Specular Color (RGB)</span></span>
  - <span data-ttu-id="a4e1f-149">Brillo</span><span class="sxs-lookup"><span data-stu-id="a4e1f-149">Shininess</span></span>
  - <span data-ttu-id="a4e1f-150">Reflexión</span><span class="sxs-lookup"><span data-stu-id="a4e1f-150">Reflectivity</span></span>
- <span data-ttu-id="a4e1f-151">No se admiten materiales personalizados</span><span class="sxs-lookup"><span data-stu-id="a4e1f-151">Custom materials are not supported</span></span>
- <span data-ttu-id="a4e1f-152">El máximo de un material por malla</span><span class="sxs-lookup"><span data-stu-id="a4e1f-152">Maximum of one material per mesh</span></span>
- <span data-ttu-id="a4e1f-153">El máximo de una capa de material</span><span class="sxs-lookup"><span data-stu-id="a4e1f-153">Maximum of one material layer</span></span>
- <span data-ttu-id="a4e1f-154">Máximo de 8 materiales por archivo</span><span class="sxs-lookup"><span data-stu-id="a4e1f-154">Maximum of 8 materials per file</span></span>

### <span data-ttu-id="a4e1f-155">Limitaciones de archivos y modelos</span><span class="sxs-lookup"><span data-stu-id="a4e1f-155">File and model limitations</span></span>

<span data-ttu-id="a4e1f-156">Hay límites duros en el tamaño de los archivos, así como el número de modelos, vértices y mallas que pueden abrirse de forma simultánea en el visor 3D:</span><span class="sxs-lookup"><span data-stu-id="a4e1f-156">There are hard limits on the size of files, as well as the number of models, vertices, and meshes that can be open simultaneously in 3D Viewer:</span></span>

- <span data-ttu-id="a4e1f-157">500 MB de tamaño máximo de archivo por modelo</span><span class="sxs-lookup"><span data-stu-id="a4e1f-157">500 MB maximum file size per model</span></span>
- <span data-ttu-id="a4e1f-158">Vértices: 600 000 combinados con todos los modelos abiertos</span><span class="sxs-lookup"><span data-stu-id="a4e1f-158">Vertices: 600,000 combined on all open models</span></span>
- <span data-ttu-id="a4e1f-159">Mallas: 1 600 combinadas en todos los modelos abiertos</span><span class="sxs-lookup"><span data-stu-id="a4e1f-159">Meshes: 1,600 combined on all open models</span></span>
- <span data-ttu-id="a4e1f-160">El máximo de 40 modelos abiertos al mismo tiempo</span><span class="sxs-lookup"><span data-stu-id="a4e1f-160">Maximum of 40 models open at one time</span></span>

## <span data-ttu-id="a4e1f-161">Optimización de modelos 3D para el visor 3D</span><span class="sxs-lookup"><span data-stu-id="a4e1f-161">Optimizing 3D models for 3D Viewer</span></span>

### <span data-ttu-id="a4e1f-162">Consideraciones especiales</span><span class="sxs-lookup"><span data-stu-id="a4e1f-162">Special considerations</span></span>

- <span data-ttu-id="a4e1f-163">Evitar los materiales negros o las áreas negras en los mapas de textura.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-163">Avoid black materials or black areas in texture maps.</span></span> <span data-ttu-id="a4e1f-164">Los hologramas están hechos de luz, por lo que HoloLens hace que el negro (la ausencia de luz) sea transparente.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-164">Holograms are made of light, thus HoloLens renders black (the absence of light) as transparent.</span></span>
- <span data-ttu-id="a4e1f-165">Antes de exportar a FBX desde su herramienta de creación, asegúrese de que toda la geometría sea visible y está desbloqueada y que ninguna de las capas que contienen la geometría esté desactivada o con plantilla.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-165">Before exporting to FBX from your creation tool, ensure all geometry is visible and unlocked and no layers that contain geometry are turned off or templated.</span></span> <span data-ttu-id="a4e1f-166">No se respeta la visibilidad.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-166">Visibility is not respected.</span></span>
- <span data-ttu-id="a4e1f-167">Evitar desplazamientos de traducción muy grandes entre nodos (por ejemplo, 100 000 unidades).</span><span class="sxs-lookup"><span data-stu-id="a4e1f-167">Avoid very large translation offsets between nodes (for example, 100,000 units).</span></span> <span data-ttu-id="a4e1f-168">Esto puede hacer que el modelo se rote mientras se mueve o se escala/gira.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-168">This can cause the model to jitter while being moved/scaled/rotated.</span></span>

### <span data-ttu-id="a4e1f-169">Optimización del rendimiento</span><span class="sxs-lookup"><span data-stu-id="a4e1f-169">Performance optimization</span></span>

<span data-ttu-id="a4e1f-170">Tenga en cuenta el performance durante la creación de contenido y validación en la aplicación Visor 3D en HoloLens durante el proceso de creación para obtener los mejores resultados.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-170">Keep performance in mind while authoring content and validate in the 3D Viewer app on HoloLens during the authoring process for best results.</span></span> <span data-ttu-id="a4e1f-171">El visor 3D representa el contenido en tiempo real y el rendimiento está sujeto a las funciones de hardware de HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-171">3D Viewer renders content real-time and performance is subject to HoloLens hardware capabilities.</span></span>  

<span data-ttu-id="a4e1f-172">Hay muchas variables en un modelo 3D que pueden afectar al rendimiento.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-172">There are many variables in a 3D model that can impact performance.</span></span> <span data-ttu-id="a4e1f-173">El visor 3D mostrará una advertencia durante la carga si hay más de 150 000 vértices o más de 400 mallas.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-173">3D Viewer will show a warning on load if there are more than 150,000 vertices or more than 400 meshes.</span></span> <span data-ttu-id="a4e1f-174">Las animaciones pueden afectar al rendimiento de otros modelos abiertos.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-174">Animations can have an impact on the performance of other open models.</span></span> <span data-ttu-id="a4e1f-175">Hay límites estrictos en el número total de modelos, vértices y mallas que pueden abrirse simultáneamente en el visor 3D (vea [Limitaciones de archivos y modelos](#file-and-model-limitations)).</span><span class="sxs-lookup"><span data-stu-id="a4e1f-175">There are also hard limits on the total number models, vertices, and meshes that can be open simultaneously in 3D Viewer (see [File and model limitations](#file-and-model-limitations)).</span></span>  

<span data-ttu-id="a4e1f-176">Si el modelo 3D no se ejecuta bien debido a la complejidad del modelo, considere:</span><span class="sxs-lookup"><span data-stu-id="a4e1f-176">If the 3D model isn't running well due to model complexity, consider:</span></span>

- <span data-ttu-id="a4e1f-177">Reducir el número de polígonos</span><span class="sxs-lookup"><span data-stu-id="a4e1f-177">Reducing polygon count</span></span>
- <span data-ttu-id="a4e1f-178">Reducir el número de huesos en la animación rigged</span><span class="sxs-lookup"><span data-stu-id="a4e1f-178">Reducing number of bones in rigged animation</span></span>
- <span data-ttu-id="a4e1f-179">Evitar la auto-oclusión</span><span class="sxs-lookup"><span data-stu-id="a4e1f-179">Avoiding self-occlusion</span></span>

<span data-ttu-id="a4e1f-180">La representación de doble cara es compatible con el visor 3D, aunque está desactivada de manera predeterminada por motivos de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-180">Double-sided rendering is supported in 3D Viewer, although it is turned off by default for performance reasons.</span></span> <span data-ttu-id="a4e1f-181">Esto se puede activar a través del botón **Doble cara** en la página **Detalles**.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-181">This can be turned on via the **Double Sided** button on the **Details** page.</span></span> <span data-ttu-id="a4e1f-182">Para obtener un rendimiento óptimo, evite tener que representar a doble cara en su contenido.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-182">For best performance, avoid the need for double-sided rendering in your content.</span></span>

### <span data-ttu-id="a4e1f-183">Validar su modelo 3D</span><span class="sxs-lookup"><span data-stu-id="a4e1f-183">Validating your 3D model</span></span>

<span data-ttu-id="a4e1f-184">Para validar su modelo, ábralo en el visor 3D en HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-184">Validate your model by opening it in 3D Viewer on HoloLens.</span></span> <span data-ttu-id="a4e1f-185">Seleccione el botón **Detalles** para ver las características de su modelo y las advertencias de contenido no compatible (si lo hay).</span><span class="sxs-lookup"><span data-stu-id="a4e1f-185">Select the **Details** button to view your model's characteristics and warnings of unsupported content (if present).</span></span>

### <span data-ttu-id="a4e1f-186">Representación de modelos 3D con dimensiones reales</span><span class="sxs-lookup"><span data-stu-id="a4e1f-186">Rendering 3D models with true-to-life dimensions</span></span>

<span data-ttu-id="a4e1f-187">De forma predeterminada, el visor 3D muestra modelos 3D con un tamaño y una posición cómodos respecto al usuario.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-187">By default, 3D Viewer displays 3D models at a comfortable size and position relative to the user.</span></span> <span data-ttu-id="a4e1f-188">Sin embargo, si el procesamiento de un modelo 3D con las medidas reales es importante (por ejemplo, al evaluar los modelos de mobiliario en una sala), el creador del contenido puede establecer un marcador en los metadatos del archivo para evitar el cambio de tamaño del modelo tanto por la aplicación como por el usuario.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-188">However, if rendering a 3D model with true-to-life measurements is important (for example, when evaluating furniture models in a room), the content creator can set a flag within the file's metadata to prevent resizing of that model by both the application and the user.</span></span>

<span data-ttu-id="a4e1f-189">Para evitar la escala del modelo, agregue un atributo personalizado de tipo booleano a cualquier objeto de la escena denominada Microsoft_DisableScale y establézcalo como true.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-189">To prevent scaling of the model, add a Boolean custom attribute to any object in the scene named Microsoft_DisableScale and set it to true.</span></span> <span data-ttu-id="a4e1f-190">El visor 3D respetará la información de FbxSystemUnit creada en el archivo FBX.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-190">3D Viewer will then respect the FbxSystemUnit information baked into the FBX file.</span></span> <span data-ttu-id="a4e1f-191">La escala en visor 3D es de 1 metro por unidad FBX.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-191">Scale in 3D Viewer is 1 meter per FBX unit.</span></span>

## <span data-ttu-id="a4e1f-192">Ver archivos FBX en HoloLens</span><span class="sxs-lookup"><span data-stu-id="a4e1f-192">Viewing FBX files on HoloLens</span></span>

### <span data-ttu-id="a4e1f-193">Abrir un archivo FBX desde Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a4e1f-193">Open an FBX file from Microsoft Edge</span></span>

<span data-ttu-id="a4e1f-194">Los archivos FBX pueden abrirse directamente desde un sitio web con Microsoft Edge en HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-194">FBX files can be opened directly from a website using Microsoft Edge on HoloLens.</span></span>

1. <span data-ttu-id="a4e1f-195">En Microsoft Edge, navegue hasta la página web que contenga el archivo FBX que quiera ver.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-195">In Microsoft Edge, navigate to the webpage containing the FBX file you want to view.</span></span>
1. <span data-ttu-id="a4e1f-196">Seleccione el archivo para descargarlo.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-196">Select the file to download it.</span></span>
1. <span data-ttu-id="a4e1f-197">Cuando termine la descarga, seleccione el botón **Abrir** en Microsoft Edge para abrir el archivo en el visor 3D.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-197">When the download is complete, select the **Open** button in Microsoft Edge to open the file in 3D Viewer.</span></span>

<span data-ttu-id="a4e1f-198">Se puede acceder al archivo descargado y volver a abrirlo más tarde utilizando Descargas en Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-198">The downloaded file can be accessed and opened again later by using Downloads in Microsoft Edge.</span></span> <span data-ttu-id="a4e1f-199">Para guardar un modelo 3D y asegurar el acceso continuo, descargue el archivo en el equipo y guárdelo en su cuenta de OneDrive.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-199">To save a 3D model and ensure continued access, download the file on your PC and save it to your OneDrive account.</span></span> <span data-ttu-id="a4e1f-200">El archivo se puede abrir desde la aplicación de OneDrive en HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-200">The file can then be opened from the OneDrive app on HoloLens.</span></span>

> [!NOTE]
> <span data-ttu-id="a4e1f-201">Algunos sitios web con modelos de FBX descargables los proporcionan en formato comprimido ZIP.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-201">Some websites with downloadable FBX models provide them in compressed ZIP format.</span></span> <span data-ttu-id="a4e1f-202">El visor 3D no puede abrir archivos ZIP directamente.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-202">3D Viewer cannot open ZIP files directly.</span></span> <span data-ttu-id="a4e1f-203">En su lugar, use su PC para extraer el archivo FBX y guardarlo en su cuenta de OneDrive.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-203">Instead, use your PC to extract the FBX file and save it to your OneDrive account.</span></span> <span data-ttu-id="a4e1f-204">El archivo se puede abrir desde la aplicación de OneDrive en HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-204">The file can then be opened from the OneDrive app on HoloLens.</span></span>

### <span data-ttu-id="a4e1f-205">Abrir un archivo FBX desde OneDrive</span><span class="sxs-lookup"><span data-stu-id="a4e1f-205">Open an FBX file from OneDrive</span></span>

<span data-ttu-id="a4e1f-206">Los archivos FBX se pueden abrir desde OneDrive con la aplicación de OneDrive en HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-206">FBX files can be opened from OneDrive by using the OneDrive app on HoloLens.</span></span> <span data-ttu-id="a4e1f-207">Asegúrese de que ha instalado OneDrive usando la aplicación de Microsoft Store en HoloLens y que ya ha subido el archivo FBX a OneDrive en su PC.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-207">Be sure you've installed OneDrive using Microsoft Store app on HoloLens and that you've already uploaded the FBX file to OneDrive on your PC.</span></span>

<span data-ttu-id="a4e1f-208">Una vez en OneDrive, puede que los archivos FBX se abran en HoloLens con el visor 3D usando uno de los dos siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="a4e1f-208">Once in OneDrive, FBX files can be opened on HoloLens using 3D Viewer in one of two ways:</span></span>

- <span data-ttu-id="a4e1f-209">Inicie OneDrive en HoloLens y seleccione el archivo FBX para abrirlo en el visor 3D.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-209">Launch OneDrive on HoloLens and select the FBX file to open it in 3D Viewer.</span></span>
- <span data-ttu-id="a4e1f-210">Inicie el visor 3D, pulse la pantalla para mostrar la barra de herramientas, y seleccione **Abrir archivo**.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-210">Launch 3D Viewer, air tap to show the toolbar, and select **Open File**.</span></span> <span data-ttu-id="a4e1f-211">Se iniciará OneDrive, lo que le permitirá seleccionar un archivo FBX.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-211">OneDrive will launch, allowing you to select an FBX file.</span></span>

## <span data-ttu-id="a4e1f-212">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="a4e1f-212">Troubleshooting</span></span>

### <span data-ttu-id="a4e1f-213">Aparecen advertencias al abrir un modelo 3D</span><span class="sxs-lookup"><span data-stu-id="a4e1f-213">I see a warning when I open a 3D model</span></span>

<span data-ttu-id="a4e1f-214">Verá una advertencia si intenta abrir un modelo 3D que contiene características que no son compatibles con el visor 3D, o si el modelo es demasiado complejo y el rendimiento puede verse afectado.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-214">You will see a warning if you attempt to open a 3D model that contains features that are not supported by 3D Viewer, or if the model is too complex and performance may be affected.</span></span> <span data-ttu-id="a4e1f-215">el visor 3D seguirá cargando el modelo 3D, pero el rendimiento o la fidelidad visual podrían verse comprometidos.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-215">3D Viewer will still load the 3D model, but performance or visual fidelity may be compromised.</span></span>

<span data-ttu-id="a4e1f-216">Para obtener más información, vea [Especificaciones de contenido compatibles](#supported-content-specifications) y [Optimizar modelos 3D para el visor 3D](#optimizing-3d-models-for-3d-viewer).</span><span class="sxs-lookup"><span data-stu-id="a4e1f-216">For more info, see [Supported content specifications](#supported-content-specifications) and [Optimizing 3D models for 3D Viewer](#optimizing-3d-models-for-3d-viewer).</span></span>

### <span data-ttu-id="a4e1f-217">Veo una advertencia y el modelo 3D no se carga.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-217">I see a warning and the 3D model doesn't load</span></span>

<span data-ttu-id="a4e1f-218">Verá un mensaje de error cuando el visor 3D no pueda cargar un modelo 3D debido a la complejidad o al tamaño del archivo, o si el archivo FBX está corrupto o no es válido.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-218">You will see an error message when 3D Viewer cannot load a 3D model due to complexity or file size, or if the FBX file is corrupt or invalid.</span></span> <span data-ttu-id="a4e1f-219">También verá un mensaje de error si se ha alcanzado el límite en el número total de modelos, vértices o mallas que pueden abrirse simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-219">You will also see an error message if you have reached the limit on the total number of models, vertices, or meshes that can be open simultaneously.</span></span>  

<span data-ttu-id="a4e1f-220">Para obtener más información, vea [Especificaciones de contenido compatibles](#supported-content-specifications) y [Limitaciones de archivo y modelo](#file-and-model-limitations).</span><span class="sxs-lookup"><span data-stu-id="a4e1f-220">For more info, see [Supported content specifications](#supported-content-specifications) and [File and model limitations](#file-and-model-limitations).</span></span>

<span data-ttu-id="a4e1f-221">Si siente que el modelo satisface las especificaciones de contenido compatibles y no ha superado las limitaciones del archivo o modelo, puede enviar el archivo FBX al equipo del visor 3D en holoapps@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-221">If you feel your model meets the supported content specifications and has not exceeded the file or model limitations, you may send your FBX file to the 3D Viewer team at holoapps@microsoft.com.</span></span> <span data-ttu-id="a4e1f-222">No podemos responder personalmente, pero tener ejemplos de archivos que no se cargan correctamente ayudará a nuestro equipo a mejorar las futuras versiones de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-222">We are not able to respond personally, but having examples of files that do not load properly will help our team improve on future versions of the app.</span></span>

### <span data-ttu-id="a4e1f-223">El modelo 3D se carga, pero no se muestra como se esperaba</span><span class="sxs-lookup"><span data-stu-id="a4e1f-223">My 3D model loads, but does not appear as expected</span></span>

<span data-ttu-id="a4e1f-224">Si el modelo 3D no se ve de la forma esperada en el visor 3D, pulse para mostrar la barra de herramientas y, a continuación, seleccione **Detalles**.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-224">If your 3D model does not look as expected in 3D Viewer, air tap to show the toolbar, then select **Details**.</span></span> <span data-ttu-id="a4e1f-225">Los aspectos del archivo que no se admiten en visor 3D se resaltarán como advertencias.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-225">Aspects of the file which are not supported by 3D Viewer will be highlighted as warnings.</span></span>

<span data-ttu-id="a4e1f-226">El problema más común que podría ver es que faltan las texturas, probablemente ya no se incrusten en el archivo FBX.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-226">The most common issue you might see is missing textures, likely because they are not embedded in the FBX file.</span></span> <span data-ttu-id="a4e1f-227">En este caso, el modelo se mostrará blanco.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-227">In this case, the model will appear white.</span></span> <span data-ttu-id="a4e1f-228">Este problema se puede solucionar en el proceso de creación al exportar desde la herramienta de creación a FBX con la opción incrustar texturas seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-228">This issue can be addressed in the creation process by exporting from your creation tool to FBX with the embed textures option selected.</span></span>

<span data-ttu-id="a4e1f-229">Para obtener más información, vea [Especificaciones de contenido compatibles](#supported-content-specifications) y [Optimizar modelos 3D para el visor 3D](#optimizing-3d-models-for-3d-viewer).</span><span class="sxs-lookup"><span data-stu-id="a4e1f-229">For more info, see [Supported content specifications](#supported-content-specifications) and [Optimizing 3D models for 3D Viewer](#optimizing-3d-models-for-3d-viewer).</span></span>

### <span data-ttu-id="a4e1f-230">Experimente caídas de rendimiento mientras visualiza el modelo 3D</span><span class="sxs-lookup"><span data-stu-id="a4e1f-230">I experience performance drops while viewing my 3D model</span></span>

<span data-ttu-id="a4e1f-231">El rendimiento al cargar y ver un modelo 3D puede verse afectado por la complejidad del modelo, el número de modelos abiertos simultáneamente o el número de modelos con animaciones activas.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-231">Performance when loading and viewing a 3D model can be affected by the complexity of the model, number of models open simultaneously, or number of models with active animations.</span></span>

<span data-ttu-id="a4e1f-232">Para obtener más información, vea [Optimización de modelos 3D para el Visor 3D](#optimizing-3d-models-for-3d-viewer) y [ Limitaciones de archivos y modelos](#file-and-model-limitations).</span><span class="sxs-lookup"><span data-stu-id="a4e1f-232">For more info, see [Optimizing 3D models for 3D Viewer](#optimizing-3d-models-for-3d-viewer) and [File and model limitations](#file-and-model-limitations).</span></span>

### <span data-ttu-id="a4e1f-233">Al abrir un archivo de FBX en HoloLens, no se abre en el visor 3D</span><span class="sxs-lookup"><span data-stu-id="a4e1f-233">When I open an FBX file on HoloLens, it doesn't open in 3D Viewer</span></span>

<span data-ttu-id="a4e1f-234">el visor 3D se asocia automáticamente a la extensión de archivo. FBX cuando se instala.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-234">3D Viewer is automatically associated with the .fbx file extension when it is installed.</span></span>

<span data-ttu-id="a4e1f-235">Si intenta abrir un archivo de FBX y ve un cuadro de diálogo que le dirige a Microsoft Store, en este momento no tiene ninguna aplicación asociada con la extensión de archivo. FBX en HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-235">If you try to open an FBX file and see a dialog box that directs you to Microsoft Store, you do not currently have an app associated with the .fbx file extension on HoloLens.</span></span>

<span data-ttu-id="a4e1f-236">Compruebe que visor 3D está instalado.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-236">Verify that 3D Viewer is installed.</span></span> <span data-ttu-id="a4e1f-237">Si no está instalado, descárguelo desde Microsoft Store en HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-237">If it is not installed, download it from Microsoft Store on HoloLens.</span></span>

<span data-ttu-id="a4e1f-238">Si visor 3D ya está instalado, inicie el visor 3D y, a continuación, vuelva a abrir el archivo.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-238">If 3D Viewer is already installed, launch 3D Viewer, then try opening the file again.</span></span> <span data-ttu-id="a4e1f-239">Si el problema persiste, desinstale y vuelva a instalar el visor 3D.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-239">If the issue persists, uninstall and reinstall 3D Viewer.</span></span> <span data-ttu-id="a4e1f-240">Se volverá a asociar la extensión de archivo. FBX con el visor 3D.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-240">This will re-associate the .fbx file extension with 3D Viewer.</span></span>

<span data-ttu-id="a4e1f-241">Si al intentar abrir un archivo de FBX, se abre una aplicación que no es 3D Viewer, es probable que esa aplicación se instale después del visor 3D y se haya expuesto en asociación con la extensión de archivo. FBX.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-241">If attempting to open an FBX file opens an app other than 3D Viewer, that app was likely installed after 3D Viewer and has taken over association with the .fbx file extension.</span></span> <span data-ttu-id="a4e1f-242">Si prefiere que la herramienta visor 3D está asociada con la extensión de archivo. FBX, desinstale y vuelva a instalar el visor 3D.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-242">If you prefer 3D Viewer to be associated with the .fbx file extension, uninstall and reinstall 3D Viewer.</span></span>

### <span data-ttu-id="a4e1f-243">El botón Abrir archivo del visor 3D no inicia ninguna aplicación</span><span class="sxs-lookup"><span data-stu-id="a4e1f-243">The Open File button in 3D Viewer doesn't launch an app</span></span>

<span data-ttu-id="a4e1f-244">El botón **Abrir archivo** abrirá la aplicación asociada a la función del selector de archivos en HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-244">The **Open File** button will open the app associated with the file picker function on HoloLens.</span></span> <span data-ttu-id="a4e1f-245">Si OneDrive está instalado, el botón **Abrir archivo** debe iniciar OneDrive.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-245">If OneDrive is installed, the **Open File** button should launch OneDrive.</span></span> <span data-ttu-id="a4e1f-246">Sin embargo, si no hay actualmente ninguna aplicación asociada a la función selector de archivos instalada en HoloLens, se le dirigirá a Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-246">However, if there is currently no app associated with the file picker function installed on HoloLens, you will be directed to Microsoft Store.</span></span>

<span data-ttu-id="a4e1f-247">Si el botón **Abrir archivo** inicia una aplicación que no sea OneDrive, es probable que esa aplicación se haya instalado después de OneDrive y haya asumido la asociación con la función del selector de archivos.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-247">If the **Open File** button launches an app other than OneDrive, that app was likely installed after OneDrive and has taken over association with the file picker function.</span></span> <span data-ttu-id="a4e1f-248">Si prefiere que OneDrive se inicie al seleccionar el botón **Abrir archivo** en el visor 3D, desinstale y vuelva a instalar OneDrive.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-248">If you prefer OneDrive to launch when selecting the **Open File** button in 3D Viewer, uninstall and reinstall OneDrive.</span></span>

<span data-ttu-id="a4e1f-249">Si no está activo el **botón Abrir archivo**, es posible que haya alcanzado el límite de modelos que se pueden abrir en el visor 3D al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-249">If the **Open File** button is not active, it's possible that you have reached the limit of models that can be open in 3D Viewer at one time.</span></span> <span data-ttu-id="a4e1f-250">Si tiene 40 modelos abiertos en el visor 3D, tendrá que cerrar algunas antes de poder abrir otros modelos.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-250">If you have 40 models open in 3D Viewer, you will need to close some before you will be able to open additional models.</span></span>

## <span data-ttu-id="a4e1f-251">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="a4e1f-251">Additional resources</span></span>

- [<span data-ttu-id="a4e1f-252">Foros de soporte técnico de Havok</span><span class="sxs-lookup"><span data-stu-id="a4e1f-252">Support forums</span></span>](http://forums.hololens.com/categories/3d-viewer-beta)
- [<span data-ttu-id="a4e1f-253">AVISOS DE TERCEROS</span><span class="sxs-lookup"><span data-stu-id="a4e1f-253">Third-party notices</span></span>](https://www.microsoft.com/{lang-locale}/legal/products)
