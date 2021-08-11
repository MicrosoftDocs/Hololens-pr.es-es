---
title: Uso de la versión beta del Visor 3D en HoloLens (1.ª generación)
description: Describe los tipos de archivos y las características que admite la versión beta del Visor 3D en HoloLens (1.ª generación), y cómo utilizar la aplicación y solucionar posibles problemas.
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
ms.openlocfilehash: d25a87bd210535e36e18f165b5461141c40aa292a07c560018ba7c0cbf76f6ba
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664934"
---
# <a name="using-3d-viewer-beta-on-hololens-1st-gen"></a>Uso de la versión beta del Visor 3D en HoloLens (1.ª generación)

La versión beta del Visor 3D le permite ver modelos 3D en HoloLens (1.ª generación). Puede abrir y ver archivos .fbx *compatibles* desde Microsoft Edge, OneDrive y otras aplicaciones.

>[!NOTE]
>Este artículo se aplica a la aplicación inmersiva **Visor 3D beta** de Unity, compatible con archivos .fbx y disponible exclusivamente en HoloLens (1.ª generación). La aplicación de **Visor 3D** instalada previamente en HoloLens 2 admite la apertura de modelos 3D .glb personalizados en el ambiente principal (consulte [Información general sobre los requisitos de recursos](/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview) para obtener más detalles).

>[!IMPORTANT]
>Aunque la versión beta del Visor 3D pueda seguir estando disponible en Microsoft Store para HoloLens (1.ª generación), no sigue en desarrollo activo y ya no es compatible.

Si tiene problemas para abrir un modelo 3D en la versión beta del Visor 3D o si algunas de las características de su modelo 3D no son compatibles, consulte [Especificaciones de contenido compatibles](#supported-content-specifications) a continuación.

Para compilar u optimizar modelos 3D para su uso con Visor 3D Beta, consulte [Optimización de modelos 3D para la versión beta del Visor 3D](#optimizing-3d-models-for-3d-viewer-beta) a continuación.

Hay dos formas de abrir un modelo 3D en HoloLens. Consulte [Ver archivos FBX en HoloLens](#viewing-fbx-files-on-hololens) a continuación para obtener más información.

Si tiene problemas después de leer estos temas, consulte [Solución de problemas](#troubleshooting) a continuación.

## <a name="supported-content-specifications"></a>Especificaciones de contenido compatibles

### <a name="file-format"></a>Formato de archivo

- Formato FBX
- Versión máxima de FBX 2015.1.0

### <a name="file-size"></a>Tamaño de archivo

- 5 KB como mínimo
- 500 MB como máximo

### <a name="geometry"></a>Geometría

- Solo modelos poligonales. Ninguna superficie de subdivisión o NURB.
- Sistema de coordenadas derecha.
- No se admite la distorsión en matrices de transformación.

### <a name="textures"></a>Texturas

- Los mapas de textura deben estar insertados en el archivo FBX.
- Formatos de imagen admitidos:
  - Imágenes JPEG y PNG.
  - Imágenes BMP (color verdadero RGB de 24 bits).
  - Imágenes TGA (color verdadero RGB de 24 bits y RGBQ de 32 bits).
- Resolución de textura máxima de 2048 x 2048.
- Máximo de un mapa de difusión, un mapa normal y un mapa de cubos de reflexión por malla.
- El canal alfa en texturas difusas hace que los píxeles se descarten por debajo de un 50 %.

### <a name="animation"></a>Animación

- Animación de escala, rotación o traslación en objetos individuales
- Animación esquelética (manipulada) con aplicación de máscaras
  - Máximo de 4 influencias por vértice

### <a name="materials"></a>Materiales

- Se admiten los materiales Lambert y Phong con parámetros ajustables.
- Propiedades de material admitidas para Lambert:
  - Textura principal (prueba RGB + Alpha)
  - Color difuso (RGB)
  - Color ambiente (RGB)
- Propiedades de material admitidas para Phong:
  - Textura principal (prueba RGB + Alpha)
  - Color difuso (RGB)
  - Color ambiente (RGB)
  - Color especular (RGB)
  - Brillo
  - Reflexión
- No se admiten materiales personalizados.
- Máximo de un material por malla.
- Máximo de una capa de material.
- Máximo de 8 materiales por archivo.

### <a name="file-and-model-limitations"></a>Limitaciones de archivos y modelos

Hay unos límites estrictos en el tamaño de los archivos y el número de modelos, vértices y mallas que pueden abrirse de forma simultánea en la versión beta del Visor 3D:

- 500 MB de tamaño máximo de archivo por modelo.
- Vértices: 600 000 combinados en todos los modelos abiertos.
- Mallas: 1600 combinadas en todos los modelos abiertos.
- Máximo de 40 modelos abiertos al mismo tiempo.

## <a name="optimizing-3d-models-for-3d-viewer-beta"></a>Optimización de modelos 3D para la versión beta del Visor 3D

### <a name="special-considerations"></a>Consideraciones especiales

- Evite los materiales negros o las áreas negras en los mapas de texturas. Los hologramas están hechos de luz, por lo que HoloLens hace que el negro (la ausencia de luz) sea transparente.
- Antes de exportar a FBX desde su herramienta de creación, asegúrese de que toda la geometría es visible y está desbloqueada y de que ninguna de las capas que contienen geometría se han desactivado o basado en modelos. La visibilidad no se respeta.
- Evite desplazamientos de traslación muy grandes entre nodos (por ejemplo, 100 000 unidades). Esto puede hacer que el modelo fluctúe mientras se mueve, escala o gira.

### <a name="performance-optimization"></a>Optimización del rendimiento

Tenga en cuenta el rendimiento siempre que cree contenido y lo valide en la aplicación de la versión beta del Visor 3D en HoloLens durante el proceso de creación para obtener los mejores resultados. La versión beta del Visor 3D representa el contenido en tiempo real y el rendimiento depende de las capacidades del hardware de HoloLens.  

Hay muchas variables en un modelo 3D que pueden afectar al rendimiento. La versión beta del Visor 3D mostrará una advertencia durante la carga cuando haya más de 150 000 vértices o más de 400 mallas. Las animaciones pueden afectar al rendimiento de otros modelos abiertos. También existen límites estrictos en el número total de modelos, vértices y mallas que pueden abrirse de forma simultánea en la versión beta del Visor 3D (consulte [Limitaciones de archivos y modelos](#file-and-model-limitations)).  

Si el modelo 3D no se ejecuta bien debido a su complejidad, considere lo siguiente:

- Reducir el número de polígonos
- Reducir el número de huesos en la animación manipulada
- Evitar la oclusión automática

La versión beta del Visor 3D admite la representación a doble cara, aunque está desactivada de manera predeterminada por motivos de rendimiento. Se puede activar mediante el botón **Doble cara** en la página **Detalles**. Para obtener un rendimiento óptimo, evite la necesidad de representación a doble cara en su contenido.

### <a name="validating-your-3d-model"></a>Validar el modelo 3D

Para validar el modelo, ábralo en la versión beta del Visor 3D en HoloLens. Seleccione el botón **Detalles** para ver las características de su modelo y las advertencias de contenido no admitido (si lo hay).

### <a name="rendering-3d-models-with-true-to-life-dimensions"></a>Representación de modelos 3D con dimensiones reales

De forma predeterminada, la versión beta del Visor 3D muestra modelos 3D con un tamaño y una posición cómodos para el usuario. Sin embargo, si la representación de un modelo 3D con medidas reales es importante (por ejemplo, al evaluar los modelos de mobiliario en una sala), el creador del contenido puede establecer un marcador en los metadatos del archivo para evitar que la aplicación y el usuario cambien el tamaño del modelo.

Para evitar el escalado del modelo, agregue un atributo booleano personalizado a cualquier objeto de la escena denominada Microsoft_DisableScale y establézcalo en true. La versión beta del Visor 3D respetará la información de FbxSystemUnit incorporada en el archivo FBX. La escala de la versión beta del Visor 3D es de un metro por unidad FBX.

## <a name="viewing-fbx-files-on-hololens"></a>Ver archivos FBX en HoloLens

### <a name="open-an-fbx-file-from-microsoft-edge"></a>Abrir un archivo FBX desde Microsoft Edge

Los archivos FBX pueden abrirse directamente desde un sitio web con Microsoft Edge en HoloLens.

1. En Microsoft Edge, navegue hasta la página web que contenga el archivo FBX que quiere ver.
1. Seleccione el archivo para descargarlo.
1. Cuando termine la descarga, seleccione el botón **Abrir** en Microsoft Edge para abrir el archivo en la versión beta del Visor 3D.

Se puede acceder al archivo descargado y volver a abrirlo más tarde con la opción Descargas de Microsoft Edge. Para guardar un modelo 3D y garantizar el acceso continuo, descargue el archivo en el equipo y guárdelo en su cuenta de OneDrive. El archivo se puede abrir desde la aplicación OneDrive en HoloLens.

> [!NOTE]
> Algunos sitios web con modelos FBX descargables los proporcionan en el formato comprimido ZIP. La versión beta del Visor 3D no puede abrir archivos ZIP directamente. En su lugar, use su equipo para extraer el archivo FBX y guardarlo en su cuenta de OneDrive. El archivo se puede abrir desde la aplicación OneDrive en HoloLens.

### <a name="open-an-fbx-file-from-onedrive"></a>Abrir un archivo FBX desde OneDrive

Los archivos FBX se pueden abrir desde OneDrive con la aplicación OneDrive en HoloLens. Asegúrese de haber instalado OneDrive con la aplicación Microsoft Store en HoloLens y haber subido el archivo FBX a OneDrive en su equipo.

Una vez en OneDrive, los archivos FBX se pueden abrir en HoloLens con la versión beta del Visor 3D usando uno de los dos siguientes métodos:

- Inicie OneDrive en HoloLens y seleccione el archivo FBX para abrirlo en la versión beta del Visor 3D.
- Inicie la versión beta del Visor 3D, pulse en el aire para mostrar la barra de herramientas y seleccione **Abrir archivo**. Se iniciará OneDrive y le permitirá seleccionar un archivo FBX.

## <a name="troubleshooting"></a>Solución de problemas

### <a name="i-see-a-warning-when-i-open-a-3d-model"></a>Aparecen advertencias al abrir un modelo 3D

Verá una advertencia si intenta abrir un modelo 3D que contiene características que no son compatibles con la versión beta del Visor 3D, o si el modelo es demasiado complejo y el rendimiento puede verse afectado. La versión beta del Visor 3D seguirá cargando el modelo 3D, pero el rendimiento o la fidelidad visual podrían verse comprometidos.

Para más información, consulte [Especificaciones de contenido compatibles](#supported-content-specifications) y [Optimización de modelos 3D para la versión beta del Visor 3D](#optimizing-3d-models-for-3d-viewer-beta).

### <a name="i-see-a-warning-and-the-3d-model-doesnt-load"></a>Se muestra una advertencia y el modelo 3D no se carga

Verá un mensaje de error cuando la versión beta del Visor 3D no pueda cargar un modelo 3D debido a la complejidad o al tamaño del archivo, o si el archivo FBX está dañado o no es válido. También verá un mensaje de error si alcanza el límite en el número total de modelos, vértices o mallas que pueden abrirse simultáneamente.  

Para más información, consulte [Especificaciones de contenido compatibles](#supported-content-specifications) y [Limitaciones de archivos y modelos](#file-and-model-limitations).

### <a name="my-3d-model-loads-but-does-not-appear-as-expected"></a>El modelo 3D se carga, pero no se muestra como se esperaba

Si el modelo 3D no se ve de la forma esperada en la versión beta del Visor 3D, pulse en el aire para mostrar la barra de herramientas y, a continuación, seleccione **Detalles**. Los aspectos del archivo que no se admitan en la versión beta del Visor 3D se resaltarán como advertencias.

El problema más común que podría ver es que faltan las texturas, probablemente porque no se insertaron en el archivo FBX. En este caso, el modelo se mostrará blanco. Este problema se puede solucionar en el proceso de creación al exportar desde la herramienta de creación a FBX con la opción de inserción de texturas seleccionada.

Para más información, consulte [Especificaciones de contenido compatibles](#supported-content-specifications) y [Optimización de modelos 3D para la versión beta del Visor 3D](#optimizing-3d-models-for-3d-viewer-beta).

### <a name="i-experience-performance-drops-while-viewing-my-3d-model"></a>Se producen caídas de rendimiento al visualizar el modelo 3D

El rendimiento al cargar y ver un modelo 3D puede verse afectado por la complejidad del modelo, el número de modelos abiertos simultáneamente o el número de modelos con animaciones activas.

Para obtener más información, vea [Optimización de modelos 3D para la versión beta del Visor 3D](#optimizing-3d-models-for-3d-viewer-beta) y [Limitaciones de archivos y modelos](#file-and-model-limitations).

### <a name="when-i-open-an-fbx-file-on-hololens-it-doesnt-open-in-3d-viewer-beta"></a>Al abrir un archivo FBX en HoloLens, no se abre con la versión beta del Visor 3D

La versión beta del Visor 3D se asocia automáticamente a la extensión de archivo .fbx cuando se instala.

Si intenta abrir un archivo FBX y ve un cuadro de diálogo que le dirige a Microsoft Store, en este momento no tiene ninguna aplicación asociada con la extensión de archivo .fbx en HoloLens.

Compruebe que la versión beta del Visor 3D está instalada. Si no está instalada, descárguela desde Microsoft Store en HoloLens.

Si la versión beta del Visor 3D ya está instalada, iníciela y, a continuación, intente volver a abrir el archivo. Si el problema persiste, desinstale y vuelva a instalar la versión beta del Visor 3D. Se volverá a asociar la extensión de archivo .fbx con la versión beta del Visor 3D.

Si al intentar abrir un archivo FBX se abre una aplicación que no es la versión beta del Visor 3D, es probable que esa aplicación se instalara después de la versión beta del Visor 3D y que asumiera la asociación con la extensión de archivo .fbx. Desinstale y vuelva a instalar la versión beta del Visor 3D si prefiere que esta aplicación se asocie con la extensión de archivo .fbx.

### <a name="the-open-file-button-in-3d-viewer-beta-doesnt-launch-an-app"></a>El botón Abrir archivo de la versión beta del Visor 3D no inicia ninguna aplicación

El botón **Abrir archivo** abrirá la aplicación asociada a la función del selector de archivos en HoloLens. Si OneDrive está instalado, el botón **Abrir archivo** debería iniciar OneDrive. Sin embargo, si no hay actualmente ninguna aplicación asociada a la función del selector de archivos instalada en HoloLens, se le dirigirá a Microsoft Store.

Si el botón **Abrir archivo** inicia una aplicación distinta de OneDrive, es probable que esa aplicación se instalara después de OneDrive y que asumiera la asociación con la función del selector de archivos. Si prefiere que OneDrive se inicie cuando seleccione el botón **Abrir archivo** de la versión beta del Visor 3D, desinstale y vuelva a instalar OneDrive.

Si el botón **Abrir archivo** no está activo, es posible que haya alcanzado el límite de modelos que se pueden abrir al mismo tiempo en la versión beta del Visor 3D. Si tiene 40 modelos abiertos en la versión beta del Visor 3D, tendrá que cerrar algunas para poder abrir más modelos.

## <a name="additional-resources"></a>Recursos adicionales

- [Foros de soporte técnico](http://forums.hololens.com/categories/3d-viewer-beta): solo con fines de archivo. Este foro ya no está activo.
- [Avisos de terceros](https://www.microsoft.com/{lang-locale}/legal/products)
