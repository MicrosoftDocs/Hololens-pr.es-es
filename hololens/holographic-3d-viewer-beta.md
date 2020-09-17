---
title: Uso de la versión beta del visor 3D en HoloLens (1.ª generación)
description: Describe los tipos de archivos y de funciones que admite la versión beta del visor 3D en HoloLens (1.ª generación) y cómo utilizar la aplicación y solucionar posibles problemas.
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
ms.openlocfilehash: f5481d6466459667deb99232fdd67c4491798cbe
ms.sourcegitcommit: 1b19b0eb552189d7c50617bbdf3a102d3c85ee0e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2020
ms.locfileid: "11016291"
---
# <span data-ttu-id="d48cd-103">Uso de la versión beta del visor 3D en HoloLens (1.ª generación)</span><span class="sxs-lookup"><span data-stu-id="d48cd-103">Using 3D Viewer Beta on HoloLens (1st gen)</span></span>

<span data-ttu-id="d48cd-104">La versión beta del visor 3D le permite ver modelos 3D utilizando HoloLens (1.ª generación).</span><span class="sxs-lookup"><span data-stu-id="d48cd-104">3D Viewer Beta lets you view 3D models on HoloLens (1st gen).</span></span> <span data-ttu-id="d48cd-105">Puede abrir y ver *compatibles*. FBX los archivos de Microsoft Edge, OneDrive y otras aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="d48cd-105">You can open and view *supported* .fbx files from Microsoft Edge, OneDrive, and other apps.</span></span>

>[!NOTE]
><span data-ttu-id="d48cd-106">Este artículo tiene su aplicación en la inmersión de la aplicación de Unity de **la versión beta del visor 3D**, compatible con archivos FBX y disponible exclusivamente en HoloLens (1.ª generación).</span><span class="sxs-lookup"><span data-stu-id="d48cd-106">This article applies to the immersive Unity **3D Viewer Beta** app, which supports .fbx files and is only available on HoloLens (1st gen).</span></span> <span data-ttu-id="d48cd-107">La aplicación preinstalada**del visor de 3D** en HoloLens 2 es compatible con la apertura de modelos personalizados. glb 3D en la realidad en la página de inicio (vea [información general sobre los requisitos de activos](https://docs.microsoft.com/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="d48cd-107">The pre-installed **3D Viewer** app on HoloLens 2 supports opening custom .glb 3D models in the mixed reality home (see [Asset requirements overview](https://docs.microsoft.com/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview) for more details.</span></span>

>[!IMPORTANT]
><span data-ttu-id="d48cd-108">Aunque la versión beta del visor 3D pueda seguir estando disponible para HoloLens (1.ª generación) en Microsoft Store, no sigue en desarrollo activo y ya no es compatible.</span><span class="sxs-lookup"><span data-stu-id="d48cd-108">While 3D Viewer Beta may remain available in the Microsoft Store for HoloLens (1st gen), it is no longer in active development and is no longer supported.</span></span>

<span data-ttu-id="d48cd-109">Si tiene problemas para abrir un modelo 3D en la versión beta del visor 3D o si algunas de las características de su modelo 3D no son compatibles, consulte a continuación [Especificaciones de contenido compatibles](#supported-content-specifications).</span><span class="sxs-lookup"><span data-stu-id="d48cd-109">If you're having trouble opening a 3D model in 3D Viewer Beta, or certain features of your 3D model are unsupported, see [Supported content specifications](#supported-content-specifications) below.</span></span>

<span data-ttu-id="d48cd-110">Para crear u optimizar modelos 3D y usarlos con la versión beta del visor 3D, consulte a continuación [Optimización de modelos 3D para la versión beta del visor 3D](#optimizing-3d-models-for-3d-viewer-beta).</span><span class="sxs-lookup"><span data-stu-id="d48cd-110">To build or optimize 3D models for use with 3D Viewer Beta, see [Optimizing 3D models for 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta) below.</span></span>

<span data-ttu-id="d48cd-111">Hay dos formas de abrir un modelo 3D en HoloLens.</span><span class="sxs-lookup"><span data-stu-id="d48cd-111">There are two ways to open a 3D model on HoloLens.</span></span> <span data-ttu-id="d48cd-112">Consulte [Ver archivos FBX en HoloLens](#viewing-fbx-files-on-hololens) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="d48cd-112">See [Viewing FBX files on HoloLens](#viewing-fbx-files-on-hololens) below to learn more.</span></span>

<span data-ttu-id="d48cd-113">Si tiene problemas después de leer estos temas, consulte [Solución de problemas](#troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="d48cd-113">If you're having trouble after reading these topics, see [Troubleshooting](#troubleshooting) below.</span></span>

## <span data-ttu-id="d48cd-114">Especificaciones de contenido compatibles</span><span class="sxs-lookup"><span data-stu-id="d48cd-114">Supported content specifications</span></span>

### <span data-ttu-id="d48cd-115">Formato de archivo</span><span class="sxs-lookup"><span data-stu-id="d48cd-115">File format</span></span>

- <span data-ttu-id="d48cd-116">Formato FBX</span><span class="sxs-lookup"><span data-stu-id="d48cd-116">FBX format</span></span>
- <span data-ttu-id="d48cd-117">Versión máxima de FBX 2015.1.0</span><span class="sxs-lookup"><span data-stu-id="d48cd-117">Maximum FBX release 2015.1.0</span></span>

### <span data-ttu-id="d48cd-118">Tamaño de archivo</span><span class="sxs-lookup"><span data-stu-id="d48cd-118">File size</span></span>

- <span data-ttu-id="d48cd-119">Mínimo 5 GB</span><span class="sxs-lookup"><span data-stu-id="d48cd-119">Minimum 5 KB</span></span>
- <span data-ttu-id="d48cd-120">Máximo 500 MB</span><span class="sxs-lookup"><span data-stu-id="d48cd-120">Maximum 500 MB</span></span>

### <span data-ttu-id="d48cd-121">Geometría</span><span class="sxs-lookup"><span data-stu-id="d48cd-121">Geometry</span></span>

- <span data-ttu-id="d48cd-122">Solo modelos poligonales.</span><span class="sxs-lookup"><span data-stu-id="d48cd-122">Polygonal models only.</span></span> <span data-ttu-id="d48cd-123">Ninguna superficie de subdivisión o NURBs</span><span class="sxs-lookup"><span data-stu-id="d48cd-123">No subdivision surfaces or NURBs</span></span>
- <span data-ttu-id="d48cd-124">Sistema de coordenadas izquierda</span><span class="sxs-lookup"><span data-stu-id="d48cd-124">Right-handed coordinate system</span></span>
- <span data-ttu-id="d48cd-125">No se admite la distorsión en matrices de transformación.</span><span class="sxs-lookup"><span data-stu-id="d48cd-125">Shear in transformation matrices is not supported</span></span>

### <span data-ttu-id="d48cd-126">Texturas</span><span class="sxs-lookup"><span data-stu-id="d48cd-126">Textures</span></span>

- <span data-ttu-id="d48cd-127">Los mapas de textura deben estar incrustados en el archivo FBX</span><span class="sxs-lookup"><span data-stu-id="d48cd-127">Texture maps must be embedded in the FBX file</span></span>
- <span data-ttu-id="d48cd-128">Formatos de imagen admitidos</span><span class="sxs-lookup"><span data-stu-id="d48cd-128">Supported image formats</span></span>
  - <span data-ttu-id="d48cd-129">Imágenes JPEG y PNG</span><span class="sxs-lookup"><span data-stu-id="d48cd-129">JPEG and PNG images</span></span>
  - <span data-ttu-id="d48cd-130">Imágenes BMP (color verdadero, RGB de 24 bits)</span><span class="sxs-lookup"><span data-stu-id="d48cd-130">BMP images (24-bit RGB true-color)</span></span>
  - <span data-ttu-id="d48cd-131">Imágenes TGA (RVA de 24 bits y 32 bits de RGBQ en color verdadero)</span><span class="sxs-lookup"><span data-stu-id="d48cd-131">TGA images (24-bit RGB and 32-bit RGBQ true-color)</span></span>
- <span data-ttu-id="d48cd-132">Resolución máxima de textura de 2048x2048</span><span class="sxs-lookup"><span data-stu-id="d48cd-132">Maximum texture resolution of 2048x2048</span></span>
- <span data-ttu-id="d48cd-133">Un máximo de un mapa de difusión, un mapa normal y un mapa de cubos de reflexión por malla</span><span class="sxs-lookup"><span data-stu-id="d48cd-133">Maximum of one diffuse map, one normal map, and one reflection cube map per mesh</span></span>
- <span data-ttu-id="d48cd-134">El canal alfa en texturas difusas hace que los píxeles se descartan si se muestra debajo 50%</span><span class="sxs-lookup"><span data-stu-id="d48cd-134">Alpha channel in diffuse textures causes pixels to be discarded if below 50%</span></span>

### <span data-ttu-id="d48cd-135">Animación</span><span class="sxs-lookup"><span data-stu-id="d48cd-135">Animation</span></span>

- <span data-ttu-id="d48cd-136">Animación de escalar/rotar/traslación en objetos individuales</span><span class="sxs-lookup"><span data-stu-id="d48cd-136">Scale/rotation/translation animation on individual objects</span></span>
- <span data-ttu-id="d48cd-137">Animación esquemática (RIGGED) con la piel</span><span class="sxs-lookup"><span data-stu-id="d48cd-137">Skeletal (rigged) animation with skinning</span></span>
  - <span data-ttu-id="d48cd-138">Máximo de 4 influencias por vértice</span><span class="sxs-lookup"><span data-stu-id="d48cd-138">Maximum of 4 influences per vertex</span></span>

### <span data-ttu-id="d48cd-139">Materiales</span><span class="sxs-lookup"><span data-stu-id="d48cd-139">Materials</span></span>

- <span data-ttu-id="d48cd-140">Se admiten materiales Lambert y Phong con parámetros ajustables.</span><span class="sxs-lookup"><span data-stu-id="d48cd-140">Lambert and Phong materials are supported, with adjustable parameters</span></span>
- <span data-ttu-id="d48cd-141">Propiedades de material compatible con Lambert</span><span class="sxs-lookup"><span data-stu-id="d48cd-141">Supported material properties for Lambert</span></span>
  - <span data-ttu-id="d48cd-142">Textura principal (prueba RGB + Alpha)</span><span class="sxs-lookup"><span data-stu-id="d48cd-142">Main Texture (RGB + Alpha Test)</span></span>
  - <span data-ttu-id="d48cd-143">Color difuso (RGB)</span><span class="sxs-lookup"><span data-stu-id="d48cd-143">Diffuse Color (RGB)</span></span>
  - <span data-ttu-id="d48cd-144">Color ambiente (RGB)</span><span class="sxs-lookup"><span data-stu-id="d48cd-144">Ambient Color (RGB)</span></span>
- <span data-ttu-id="d48cd-145">Propiedades de material admitidas para Phong</span><span class="sxs-lookup"><span data-stu-id="d48cd-145">Supported material properties for Phong</span></span>
  - <span data-ttu-id="d48cd-146">Textura principal (prueba RGB + Alpha)</span><span class="sxs-lookup"><span data-stu-id="d48cd-146">Main Texture (RGB + Alpha Test)</span></span>
  - <span data-ttu-id="d48cd-147">Color difuso (RGB)</span><span class="sxs-lookup"><span data-stu-id="d48cd-147">Diffuse Color (RGB)</span></span>
  - <span data-ttu-id="d48cd-148">Color ambiente (RGB)</span><span class="sxs-lookup"><span data-stu-id="d48cd-148">Ambient Color (RGB)</span></span>
  - <span data-ttu-id="d48cd-149">Color especular (RGB)</span><span class="sxs-lookup"><span data-stu-id="d48cd-149">Specular Color (RGB)</span></span>
  - <span data-ttu-id="d48cd-150">Brillo</span><span class="sxs-lookup"><span data-stu-id="d48cd-150">Shininess</span></span>
  - <span data-ttu-id="d48cd-151">Reflexión</span><span class="sxs-lookup"><span data-stu-id="d48cd-151">Reflectivity</span></span>
- <span data-ttu-id="d48cd-152">No se admiten materiales personalizados</span><span class="sxs-lookup"><span data-stu-id="d48cd-152">Custom materials are not supported</span></span>
- <span data-ttu-id="d48cd-153">El máximo de un material por malla</span><span class="sxs-lookup"><span data-stu-id="d48cd-153">Maximum of one material per mesh</span></span>
- <span data-ttu-id="d48cd-154">El máximo de una capa de material</span><span class="sxs-lookup"><span data-stu-id="d48cd-154">Maximum of one material layer</span></span>
- <span data-ttu-id="d48cd-155">Máximo de 8 materiales por archivo</span><span class="sxs-lookup"><span data-stu-id="d48cd-155">Maximum of 8 materials per file</span></span>

### <span data-ttu-id="d48cd-156">Limitaciones de archivos y modelos</span><span class="sxs-lookup"><span data-stu-id="d48cd-156">File and model limitations</span></span>

<span data-ttu-id="d48cd-157">Hay unos claros límites para el tamaño de los archivos y para el número de modelos, vértices y mallas que pueden abrirse de forma simultánea en la versión beta del visor 3D:</span><span class="sxs-lookup"><span data-stu-id="d48cd-157">There are hard limits on the size of files, as well as the number of models, vertices, and meshes that can be open simultaneously in 3D Viewer Beta:</span></span>

- <span data-ttu-id="d48cd-158">500 MB de tamaño máximo de archivo por modelo</span><span class="sxs-lookup"><span data-stu-id="d48cd-158">500 MB maximum file size per model</span></span>
- <span data-ttu-id="d48cd-159">Vértices: 600 000 combinados con todos los modelos abiertos</span><span class="sxs-lookup"><span data-stu-id="d48cd-159">Vertices: 600,000 combined on all open models</span></span>
- <span data-ttu-id="d48cd-160">Mallas: 1 600 combinadas en todos los modelos abiertos</span><span class="sxs-lookup"><span data-stu-id="d48cd-160">Meshes: 1,600 combined on all open models</span></span>
- <span data-ttu-id="d48cd-161">El máximo de 40 modelos abiertos al mismo tiempo</span><span class="sxs-lookup"><span data-stu-id="d48cd-161">Maximum of 40 models open at one time</span></span>

## <span data-ttu-id="d48cd-162">Optimización de modelos 3D para la versión beta del visor 3D</span><span class="sxs-lookup"><span data-stu-id="d48cd-162">Optimizing 3D models for 3D Viewer Beta</span></span>

### <span data-ttu-id="d48cd-163">Consideraciones especiales</span><span class="sxs-lookup"><span data-stu-id="d48cd-163">Special considerations</span></span>

- <span data-ttu-id="d48cd-164">Evitar los materiales negros o las áreas negras en los mapas de textura.</span><span class="sxs-lookup"><span data-stu-id="d48cd-164">Avoid black materials or black areas in texture maps.</span></span> <span data-ttu-id="d48cd-165">Los hologramas están hechos de luz, por lo que HoloLens hace que el negro (la ausencia de luz) sea transparente.</span><span class="sxs-lookup"><span data-stu-id="d48cd-165">Holograms are made of light, thus HoloLens renders black (the absence of light) as transparent.</span></span>
- <span data-ttu-id="d48cd-166">Antes de exportar a FBX desde su herramienta de creación, asegúrese de que toda la geometría sea visible y está desbloqueada y que ninguna de las capas que contienen la geometría esté desactivada o con plantilla.</span><span class="sxs-lookup"><span data-stu-id="d48cd-166">Before exporting to FBX from your creation tool, ensure all geometry is visible and unlocked and no layers that contain geometry are turned off or templated.</span></span> <span data-ttu-id="d48cd-167">No se respeta la visibilidad.</span><span class="sxs-lookup"><span data-stu-id="d48cd-167">Visibility is not respected.</span></span>
- <span data-ttu-id="d48cd-168">Evitar desplazamientos de traducción muy grandes entre nodos (por ejemplo, 100 000 unidades).</span><span class="sxs-lookup"><span data-stu-id="d48cd-168">Avoid very large translation offsets between nodes (for example, 100,000 units).</span></span> <span data-ttu-id="d48cd-169">Esto puede hacer que el modelo se rote mientras se mueve o se escala/gira.</span><span class="sxs-lookup"><span data-stu-id="d48cd-169">This can cause the model to jitter while being moved/scaled/rotated.</span></span>

### <span data-ttu-id="d48cd-170">Optimización del rendimiento</span><span class="sxs-lookup"><span data-stu-id="d48cd-170">Performance optimization</span></span>

<span data-ttu-id="d48cd-171">Tenga en cuenta el rendimiento siempre que crees contenido y valides en la aplicación de la versión beta del visor 3D en HoloLens durante el proceso de creación para obtener los mejores resultados.</span><span class="sxs-lookup"><span data-stu-id="d48cd-171">Keep performance in mind while authoring content and validate in the 3D Viewer Beta app on HoloLens during the authoring process for best results.</span></span> <span data-ttu-id="d48cd-172">La versión beta del visor 3D representa el contenido en tiempo real y el rendimiento depende de las capacidades del hardware de HoloLens.</span><span class="sxs-lookup"><span data-stu-id="d48cd-172">3D Viewer Beta renders content real-time and performance is subject to HoloLens hardware capabilities.</span></span>  

<span data-ttu-id="d48cd-173">Hay muchas variables en un modelo 3D que pueden afectar al rendimiento.</span><span class="sxs-lookup"><span data-stu-id="d48cd-173">There are many variables in a 3D model that can impact performance.</span></span> <span data-ttu-id="d48cd-174">La versión beta del visor 3D mostrará una advertencia durante la carga cuando haya más de 150 000 vértices o más de 400 mallas.</span><span class="sxs-lookup"><span data-stu-id="d48cd-174">3D Viewer Beta will show a warning on load if there are more than 150,000 vertices or more than 400 meshes.</span></span> <span data-ttu-id="d48cd-175">Las animaciones pueden afectar al rendimiento de otros modelos abiertos.</span><span class="sxs-lookup"><span data-stu-id="d48cd-175">Animations can have an impact on the performance of other open models.</span></span> <span data-ttu-id="d48cd-176">También hay unos límites claros en el número total de modelos, vértices y mallas que pueden abrirse de forma simultánea en la versión beta del visor 3D (consulte [Limitaciones de archivos y modelos](#file-and-model-limitations)).</span><span class="sxs-lookup"><span data-stu-id="d48cd-176">There are also hard limits on the total number models, vertices, and meshes that can be open simultaneously in 3D Viewer Beta (see [File and model limitations](#file-and-model-limitations)).</span></span>  

<span data-ttu-id="d48cd-177">Si el modelo 3D no se ejecuta bien debido a la complejidad del modelo, considere:</span><span class="sxs-lookup"><span data-stu-id="d48cd-177">If the 3D model isn't running well due to model complexity, consider:</span></span>

- <span data-ttu-id="d48cd-178">Reducir el número de polígonos</span><span class="sxs-lookup"><span data-stu-id="d48cd-178">Reducing polygon count</span></span>
- <span data-ttu-id="d48cd-179">Reducir el número de huesos en la animación rigged</span><span class="sxs-lookup"><span data-stu-id="d48cd-179">Reducing number of bones in rigged animation</span></span>
- <span data-ttu-id="d48cd-180">Evitar la auto-oclusión</span><span class="sxs-lookup"><span data-stu-id="d48cd-180">Avoiding self-occlusion</span></span>

<span data-ttu-id="d48cd-181">La versión beta del visor 3D admite la representación a doble cara, aunque está desactivada de manera predeterminada por motivos de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="d48cd-181">Double-sided rendering is supported in 3D Viewer Beta, although it is turned off by default for performance reasons.</span></span> <span data-ttu-id="d48cd-182">Esto se puede activar a través del botón **Doble cara** en la página **Detalles**.</span><span class="sxs-lookup"><span data-stu-id="d48cd-182">This can be turned on via the **Double Sided** button on the **Details** page.</span></span> <span data-ttu-id="d48cd-183">Para obtener un rendimiento óptimo, evite tener que representar a doble cara en su contenido.</span><span class="sxs-lookup"><span data-stu-id="d48cd-183">For best performance, avoid the need for double-sided rendering in your content.</span></span>

### <span data-ttu-id="d48cd-184">Validar su modelo 3D</span><span class="sxs-lookup"><span data-stu-id="d48cd-184">Validating your 3D model</span></span>

<span data-ttu-id="d48cd-185">Para validar su modelo, ábralo en la versión beta del visor 3D en HoloLens.</span><span class="sxs-lookup"><span data-stu-id="d48cd-185">Validate your model by opening it in 3D Viewer Beta on HoloLens.</span></span> <span data-ttu-id="d48cd-186">Seleccione el botón **Detalles** para ver las características de su modelo y las advertencias de contenido no compatible (si lo hay).</span><span class="sxs-lookup"><span data-stu-id="d48cd-186">Select the **Details** button to view your model's characteristics and warnings of unsupported content (if present).</span></span>

### <span data-ttu-id="d48cd-187">Representación de modelos 3D con dimensiones reales</span><span class="sxs-lookup"><span data-stu-id="d48cd-187">Rendering 3D models with true-to-life dimensions</span></span>

<span data-ttu-id="d48cd-188">De forma predeterminada, la versión beta del visor 3D muestra modelos 3D con un tamaño y una posición cómodos para el usuario.</span><span class="sxs-lookup"><span data-stu-id="d48cd-188">By default, 3D Viewer Beta displays 3D models at a comfortable size and position relative to the user.</span></span> <span data-ttu-id="d48cd-189">Sin embargo, si el procesamiento de un modelo 3D con las medidas reales es importante (por ejemplo, al evaluar los modelos de mobiliario en una sala), el creador del contenido puede establecer un marcador en los metadatos del archivo para evitar el cambio de tamaño del modelo tanto por la aplicación como por el usuario.</span><span class="sxs-lookup"><span data-stu-id="d48cd-189">However, if rendering a 3D model with true-to-life measurements is important (for example, when evaluating furniture models in a room), the content creator can set a flag within the file's metadata to prevent resizing of that model by both the application and the user.</span></span>

<span data-ttu-id="d48cd-190">Para evitar la escala del modelo, agregue un atributo personalizado de tipo booleano a cualquier objeto de la escena denominada Microsoft_DisableScale y establézcalo como true.</span><span class="sxs-lookup"><span data-stu-id="d48cd-190">To prevent scaling of the model, add a Boolean custom attribute to any object in the scene named Microsoft_DisableScale and set it to true.</span></span> <span data-ttu-id="d48cd-191">La versión beta del visor 3D respetará la información de FbxSystemUnit incorporada en el archivo FBX.</span><span class="sxs-lookup"><span data-stu-id="d48cd-191">3D Viewer Beta will then respect the FbxSystemUnit information baked into the FBX file.</span></span> <span data-ttu-id="d48cd-192">La escala en la versión beta del visor 3D es de un metro por cada unidad FBX.</span><span class="sxs-lookup"><span data-stu-id="d48cd-192">Scale in 3D Viewer Beta is 1 meter per FBX unit.</span></span>

## <span data-ttu-id="d48cd-193">Ver archivos FBX en HoloLens</span><span class="sxs-lookup"><span data-stu-id="d48cd-193">Viewing FBX files on HoloLens</span></span>

### <span data-ttu-id="d48cd-194">Abrir un archivo FBX desde Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="d48cd-194">Open an FBX file from Microsoft Edge</span></span>

<span data-ttu-id="d48cd-195">Los archivos FBX pueden abrirse directamente desde un sitio web con Microsoft Edge en HoloLens.</span><span class="sxs-lookup"><span data-stu-id="d48cd-195">FBX files can be opened directly from a website using Microsoft Edge on HoloLens.</span></span>

1. <span data-ttu-id="d48cd-196">En Microsoft Edge, navegue hasta la página web que contenga el archivo FBX que quiera ver.</span><span class="sxs-lookup"><span data-stu-id="d48cd-196">In Microsoft Edge, navigate to the webpage containing the FBX file you want to view.</span></span>
1. <span data-ttu-id="d48cd-197">Seleccione el archivo para descargarlo.</span><span class="sxs-lookup"><span data-stu-id="d48cd-197">Select the file to download it.</span></span>
1. <span data-ttu-id="d48cd-198">Cuando termine la descarga, seleccione el botón **Abrir** en Microsoft Edge para abrir el archivo en la versión beta del visor 3D.</span><span class="sxs-lookup"><span data-stu-id="d48cd-198">When the download is complete, select the **Open** button in Microsoft Edge to open the file in 3D Viewer Beta.</span></span>

<span data-ttu-id="d48cd-199">Se puede acceder al archivo descargado y volver a abrirlo más tarde utilizando Descargas en Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="d48cd-199">The downloaded file can be accessed and opened again later by using Downloads in Microsoft Edge.</span></span> <span data-ttu-id="d48cd-200">Para guardar un modelo 3D y asegurar el acceso continuo, descargue el archivo en el equipo y guárdelo en su cuenta de OneDrive.</span><span class="sxs-lookup"><span data-stu-id="d48cd-200">To save a 3D model and ensure continued access, download the file on your PC and save it to your OneDrive account.</span></span> <span data-ttu-id="d48cd-201">El archivo se puede abrir desde la aplicación de OneDrive en HoloLens.</span><span class="sxs-lookup"><span data-stu-id="d48cd-201">The file can then be opened from the OneDrive app on HoloLens.</span></span>

> [!NOTE]
> <span data-ttu-id="d48cd-202">Algunos sitios web con modelos de FBX descargables los proporcionan en formato comprimido ZIP.</span><span class="sxs-lookup"><span data-stu-id="d48cd-202">Some websites with downloadable FBX models provide them in compressed ZIP format.</span></span> <span data-ttu-id="d48cd-203">La versión beta del visor 3D no puede abrir archivos ZIP directamente.</span><span class="sxs-lookup"><span data-stu-id="d48cd-203">3D Viewer Beta cannot open ZIP files directly.</span></span> <span data-ttu-id="d48cd-204">En su lugar, use su PC para extraer el archivo FBX y guardarlo en su cuenta de OneDrive.</span><span class="sxs-lookup"><span data-stu-id="d48cd-204">Instead, use your PC to extract the FBX file and save it to your OneDrive account.</span></span> <span data-ttu-id="d48cd-205">El archivo se puede abrir desde la aplicación de OneDrive en HoloLens.</span><span class="sxs-lookup"><span data-stu-id="d48cd-205">The file can then be opened from the OneDrive app on HoloLens.</span></span>

### <span data-ttu-id="d48cd-206">Abrir un archivo FBX desde OneDrive</span><span class="sxs-lookup"><span data-stu-id="d48cd-206">Open an FBX file from OneDrive</span></span>

<span data-ttu-id="d48cd-207">Los archivos FBX se pueden abrir desde OneDrive con la aplicación de OneDrive en HoloLens.</span><span class="sxs-lookup"><span data-stu-id="d48cd-207">FBX files can be opened from OneDrive by using the OneDrive app on HoloLens.</span></span> <span data-ttu-id="d48cd-208">Asegúrese de que ha instalado OneDrive usando la aplicación de Microsoft Store en HoloLens y que ya ha subido el archivo FBX a OneDrive en su PC.</span><span class="sxs-lookup"><span data-stu-id="d48cd-208">Be sure you've installed OneDrive using Microsoft Store app on HoloLens and that you've already uploaded the FBX file to OneDrive on your PC.</span></span>

<span data-ttu-id="d48cd-209">Una vez en OneDrive, puede que los archivos FBX se abran en HoloLens con la versión beta del visor 3D usando uno de los dos siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="d48cd-209">Once in OneDrive, FBX files can be opened on HoloLens using 3D Viewer Beta in one of two ways:</span></span>

- <span data-ttu-id="d48cd-210">Inicie OneDrive en HoloLens y seleccione el archivo FBX para abrirlo en la versión beta del visor 3D.</span><span class="sxs-lookup"><span data-stu-id="d48cd-210">Launch OneDrive on HoloLens and select the FBX file to open it in 3D Viewer Beta.</span></span>
- <span data-ttu-id="d48cd-211">Inicie la versión beta del visor 3D, pulse la pantalla para mostrar la barra de herramientas, y seleccione **Abrir archivo**.</span><span class="sxs-lookup"><span data-stu-id="d48cd-211">Launch 3D Viewer Beta, air tap to show the toolbar, and select **Open File**.</span></span> <span data-ttu-id="d48cd-212">Se iniciará OneDrive, lo que le permitirá seleccionar un archivo FBX.</span><span class="sxs-lookup"><span data-stu-id="d48cd-212">OneDrive will launch, allowing you to select an FBX file.</span></span>

## <span data-ttu-id="d48cd-213">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="d48cd-213">Troubleshooting</span></span>

### <span data-ttu-id="d48cd-214">Aparecen advertencias al abrir un modelo 3D</span><span class="sxs-lookup"><span data-stu-id="d48cd-214">I see a warning when I open a 3D model</span></span>

<span data-ttu-id="d48cd-215">Verá una advertencia si intenta abrir un modelo 3D que contiene características que no son compatibles con la versión beta del visor 3D, o si el modelo es demasiado complejo y el rendimiento puede verse afectado.</span><span class="sxs-lookup"><span data-stu-id="d48cd-215">You will see a warning if you attempt to open a 3D model that contains features that are not supported by 3D Viewer Beta, or if the model is too complex and performance may be affected.</span></span> <span data-ttu-id="d48cd-216">La versión beta del visor 3D seguirá cargando el modelo 3D, pero el rendimiento o la fidelidad visual podrían verse comprometidos.</span><span class="sxs-lookup"><span data-stu-id="d48cd-216">3D Viewer Beta will still load the 3D model, but performance or visual fidelity may be compromised.</span></span>

<span data-ttu-id="d48cd-217">Para obtener más información, vea [Especificaciones de contenido compatibles](#supported-content-specifications) y [Optimizar modelos 3D para la versión beta del visor 3D](#optimizing-3d-models-for-3d-viewer-beta).</span><span class="sxs-lookup"><span data-stu-id="d48cd-217">For more info, see [Supported content specifications](#supported-content-specifications) and [Optimizing 3D models for 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta).</span></span>

### <span data-ttu-id="d48cd-218">Veo una advertencia y el modelo 3D no se carga.</span><span class="sxs-lookup"><span data-stu-id="d48cd-218">I see a warning and the 3D model doesn't load</span></span>

<span data-ttu-id="d48cd-219">Verá un mensaje de error cuando la versión beta del visor 3D no pueda cargar un modelo 3D debido a la complejidad o al tamaño del archivo, o si el archivo FBX está corrupto o no es válido.</span><span class="sxs-lookup"><span data-stu-id="d48cd-219">You will see an error message when 3D Viewer Beta cannot load a 3D model due to complexity or file size, or if the FBX file is corrupt or invalid.</span></span> <span data-ttu-id="d48cd-220">También verá un mensaje de error si se ha alcanzado el límite en el número total de modelos, vértices o mallas que pueden abrirse simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="d48cd-220">You will also see an error message if you have reached the limit on the total number of models, vertices, or meshes that can be open simultaneously.</span></span>  

<span data-ttu-id="d48cd-221">Para obtener más información, vea [Especificaciones de contenido compatibles](#supported-content-specifications) y [Limitaciones de archivo y modelo](#file-and-model-limitations).</span><span class="sxs-lookup"><span data-stu-id="d48cd-221">For more info, see [Supported content specifications](#supported-content-specifications) and [File and model limitations](#file-and-model-limitations).</span></span>

### <span data-ttu-id="d48cd-222">El modelo 3D se carga, pero no se muestra como se esperaba</span><span class="sxs-lookup"><span data-stu-id="d48cd-222">My 3D model loads, but does not appear as expected</span></span>

<span data-ttu-id="d48cd-223">Si el modelo 3D no se ve de la forma esperada en la versión beta del visor 3D, pulse para mostrar la barra de herramientas y, a continuación, seleccione **Detalles**.</span><span class="sxs-lookup"><span data-stu-id="d48cd-223">If your 3D model does not look as expected in 3D Viewer Beta, air tap to show the toolbar, then select **Details**.</span></span> <span data-ttu-id="d48cd-224">Los aspectos del archivo que no se admiten en la versión beta del visor 3D se resaltarán como advertencias.</span><span class="sxs-lookup"><span data-stu-id="d48cd-224">Aspects of the file which are not supported by 3D Viewer Beta will be highlighted as warnings.</span></span>

<span data-ttu-id="d48cd-225">El problema más común que podría ver es que faltan las texturas, probablemente ya no se incrusten en el archivo FBX.</span><span class="sxs-lookup"><span data-stu-id="d48cd-225">The most common issue you might see is missing textures, likely because they are not embedded in the FBX file.</span></span> <span data-ttu-id="d48cd-226">En este caso, el modelo se mostrará blanco.</span><span class="sxs-lookup"><span data-stu-id="d48cd-226">In this case, the model will appear white.</span></span> <span data-ttu-id="d48cd-227">Este problema se puede solucionar en el proceso de creación al exportar desde la herramienta de creación a FBX con la opción incrustar texturas seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d48cd-227">This issue can be addressed in the creation process by exporting from your creation tool to FBX with the embed textures option selected.</span></span>

<span data-ttu-id="d48cd-228">Para obtener más información, vea [Especificaciones de contenido compatibles](#supported-content-specifications) y [Optimizar modelos 3D para la versión beta del visor 3D](#optimizing-3d-models-for-3d-viewer-beta).</span><span class="sxs-lookup"><span data-stu-id="d48cd-228">For more info, see [Supported content specifications](#supported-content-specifications) and [Optimizing 3D models for 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta).</span></span>

### <span data-ttu-id="d48cd-229">Experimente caídas de rendimiento mientras visualiza el modelo 3D</span><span class="sxs-lookup"><span data-stu-id="d48cd-229">I experience performance drops while viewing my 3D model</span></span>

<span data-ttu-id="d48cd-230">El rendimiento al cargar y ver un modelo 3D puede verse afectado por la complejidad del modelo, el número de modelos abiertos simultáneamente o el número de modelos con animaciones activas.</span><span class="sxs-lookup"><span data-stu-id="d48cd-230">Performance when loading and viewing a 3D model can be affected by the complexity of the model, number of models open simultaneously, or number of models with active animations.</span></span>

<span data-ttu-id="d48cd-231">Para obtener más información, vea [Optimización de modelos 3D para la versión beta del Visor 3D](#optimizing-3d-models-for-3d-viewer-beta) y [ Limitaciones de archivos y modelos](#file-and-model-limitations).</span><span class="sxs-lookup"><span data-stu-id="d48cd-231">For more info, see [Optimizing 3D models for 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta) and [File and model limitations](#file-and-model-limitations).</span></span>

### <span data-ttu-id="d48cd-232">Al abrir un archivo de FBX en HoloLens, no se abre en la versión beta del visor 3D</span><span class="sxs-lookup"><span data-stu-id="d48cd-232">When I open an FBX file on HoloLens, it doesn't open in 3D Viewer Beta</span></span>

<span data-ttu-id="d48cd-233">La versión beta del visor 3D se asocia automáticamente a la extensión de archivo. FBX cuando se instala.</span><span class="sxs-lookup"><span data-stu-id="d48cd-233">3D Viewer Beta is automatically associated with the .fbx file extension when it is installed.</span></span>

<span data-ttu-id="d48cd-234">Si intenta abrir un archivo de FBX y ve un cuadro de diálogo que le dirige a Microsoft Store, en este momento no tiene ninguna aplicación asociada con la extensión de archivo. FBX en HoloLens.</span><span class="sxs-lookup"><span data-stu-id="d48cd-234">If you try to open an FBX file and see a dialog box that directs you to Microsoft Store, you do not currently have an app associated with the .fbx file extension on HoloLens.</span></span>

<span data-ttu-id="d48cd-235">Compruebe que la versión beta del visor 3D está instalado.</span><span class="sxs-lookup"><span data-stu-id="d48cd-235">Verify that 3D Viewer Beta is installed.</span></span> <span data-ttu-id="d48cd-236">Si no está instalado, descárguelo desde Microsoft Store en HoloLens.</span><span class="sxs-lookup"><span data-stu-id="d48cd-236">If it is not installed, download it from Microsoft Store on HoloLens.</span></span>

<span data-ttu-id="d48cd-237">Si la versión beta del visor 3D ya está instalado, iníciela y, a continuación, vuelva a abrir el archivo.</span><span class="sxs-lookup"><span data-stu-id="d48cd-237">If 3D Viewer Beta is already installed, launch 3D Viewer Beta, then try opening the file again.</span></span> <span data-ttu-id="d48cd-238">Si el problema persiste, desinstale y vuelva a instalar la versión beta del visor 3D.</span><span class="sxs-lookup"><span data-stu-id="d48cd-238">If the issue persists, uninstall and reinstall 3D Viewer Beta.</span></span> <span data-ttu-id="d48cd-239">Se volverá a asociar la extensión de archivo FBX con la versión beta del visor 3D.</span><span class="sxs-lookup"><span data-stu-id="d48cd-239">This will re-associate the .fbx file extension with 3D Viewer Beta.</span></span>

<span data-ttu-id="d48cd-240">Si al intentar abrir un archivo de FBX se abre una aplicación que no es la versión beta del visor 3D, es probable que esa aplicación se instale después de la versión beta del visor 3D y que haya asumido la asociación con la extensión de archivo FBX.</span><span class="sxs-lookup"><span data-stu-id="d48cd-240">If attempting to open an FBX file opens an app other than 3D Viewer Beta, that app was likely installed after 3D Viewer Beta and has taken over association with the .fbx file extension.</span></span> <span data-ttu-id="d48cd-241">Desinstale y vuelva a instalar la versión beta del visor 3D si prefiere que esta esté asociada con la extensión de archivo FBX.</span><span class="sxs-lookup"><span data-stu-id="d48cd-241">If you prefer 3D Viewer Beta to be associated with the .fbx file extension, uninstall and reinstall 3D Viewer Beta.</span></span>

### <span data-ttu-id="d48cd-242">El botón Abrir archivo de la versión beta del visor 3D no inicia ninguna aplicación</span><span class="sxs-lookup"><span data-stu-id="d48cd-242">The Open File button in 3D Viewer Beta doesn't launch an app</span></span>

<span data-ttu-id="d48cd-243">El botón **Abrir archivo** abrirá la aplicación asociada a la función del selector de archivos en HoloLens.</span><span class="sxs-lookup"><span data-stu-id="d48cd-243">The **Open File** button will open the app associated with the file picker function on HoloLens.</span></span> <span data-ttu-id="d48cd-244">Si OneDrive está instalado, el botón **Abrir archivo** debe iniciar OneDrive.</span><span class="sxs-lookup"><span data-stu-id="d48cd-244">If OneDrive is installed, the **Open File** button should launch OneDrive.</span></span> <span data-ttu-id="d48cd-245">Sin embargo, si no hay actualmente ninguna aplicación asociada a la función selector de archivos instalada en HoloLens, se le dirigirá a Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="d48cd-245">However, if there is currently no app associated with the file picker function installed on HoloLens, you will be directed to Microsoft Store.</span></span>

<span data-ttu-id="d48cd-246">Si el botón **Abrir archivo** inicia una aplicación que no sea OneDrive, es probable que esa aplicación se haya instalado después de OneDrive y haya asumido la asociación con la función del selector de archivos.</span><span class="sxs-lookup"><span data-stu-id="d48cd-246">If the **Open File** button launches an app other than OneDrive, that app was likely installed after OneDrive and has taken over association with the file picker function.</span></span> <span data-ttu-id="d48cd-247">Si prefiere que OneDrive se inicie cuando seleccione el botón **Abrir archivo** de la versión beta del visor 3D, desinstale y vuelva a instalar OneDrive.</span><span class="sxs-lookup"><span data-stu-id="d48cd-247">If you prefer OneDrive to launch when selecting the **Open File** button in 3D Viewer Beta, uninstall and reinstall OneDrive.</span></span>

<span data-ttu-id="d48cd-248">Si el botón **Abrir archivo** no está activo, es posible que haya alcanzado el límite de modelos que se pueden abrir al mismo tiempo en la versión beta del visor 3D.</span><span class="sxs-lookup"><span data-stu-id="d48cd-248">If the **Open File** button is not active, it's possible that you have reached the limit of models that can be open in 3D Viewer Beta at one time.</span></span> <span data-ttu-id="d48cd-249">Si tiene 40 modelos abiertos en la versión beta del visor 3D, tendrá que cerrar algunas antes de poder abrir más modelos.</span><span class="sxs-lookup"><span data-stu-id="d48cd-249">If you have 40 models open in 3D Viewer Beta, you will need to close some before you will be able to open additional models.</span></span>

## <span data-ttu-id="d48cd-250">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="d48cd-250">Additional resources</span></span>

- <span data-ttu-id="d48cd-251">[Foros de soporte](http://forums.hololens.com/categories/3d-viewer-beta): Solo para archivar.</span><span class="sxs-lookup"><span data-stu-id="d48cd-251">[Support forums](http://forums.hololens.com/categories/3d-viewer-beta) - For archival purposes only.</span></span> <span data-ttu-id="d48cd-252">Este foro ya no está activo.</span><span class="sxs-lookup"><span data-stu-id="d48cd-252">This forum is no longer active.</span></span>
- [<span data-ttu-id="d48cd-253">AVISOS DE TERCEROS</span><span class="sxs-lookup"><span data-stu-id="d48cd-253">Third-party notices</span></span>](https://www.microsoft.com/{lang-locale}/legal/products)
