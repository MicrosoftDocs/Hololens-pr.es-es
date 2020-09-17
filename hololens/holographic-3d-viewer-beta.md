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
# Uso de la versión beta del visor 3D en HoloLens (1.ª generación)

La versión beta del visor 3D le permite ver modelos 3D utilizando HoloLens (1.ª generación). Puede abrir y ver *compatibles*. FBX los archivos de Microsoft Edge, OneDrive y otras aplicaciones.

>[!NOTE]
>Este artículo tiene su aplicación en la inmersión de la aplicación de Unity de **la versión beta del visor 3D**, compatible con archivos FBX y disponible exclusivamente en HoloLens (1.ª generación). La aplicación preinstalada**del visor de 3D** en HoloLens 2 es compatible con la apertura de modelos personalizados. glb 3D en la realidad en la página de inicio (vea [información general sobre los requisitos de activos](https://docs.microsoft.com/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview) para obtener más información.

>[!IMPORTANT]
>Aunque la versión beta del visor 3D pueda seguir estando disponible para HoloLens (1.ª generación) en Microsoft Store, no sigue en desarrollo activo y ya no es compatible.

Si tiene problemas para abrir un modelo 3D en la versión beta del visor 3D o si algunas de las características de su modelo 3D no son compatibles, consulte a continuación [Especificaciones de contenido compatibles](#supported-content-specifications).

Para crear u optimizar modelos 3D y usarlos con la versión beta del visor 3D, consulte a continuación [Optimización de modelos 3D para la versión beta del visor 3D](#optimizing-3d-models-for-3d-viewer-beta).

Hay dos formas de abrir un modelo 3D en HoloLens. Consulte [Ver archivos FBX en HoloLens](#viewing-fbx-files-on-hololens) para obtener más información.

Si tiene problemas después de leer estos temas, consulte [Solución de problemas](#troubleshooting).

## Especificaciones de contenido compatibles

### Formato de archivo

- Formato FBX
- Versión máxima de FBX 2015.1.0

### Tamaño de archivo

- Mínimo 5 GB
- Máximo 500 MB

### Geometría

- Solo modelos poligonales. Ninguna superficie de subdivisión o NURBs
- Sistema de coordenadas izquierda
- No se admite la distorsión en matrices de transformación.

### Texturas

- Los mapas de textura deben estar incrustados en el archivo FBX
- Formatos de imagen admitidos
  - Imágenes JPEG y PNG
  - Imágenes BMP (color verdadero, RGB de 24 bits)
  - Imágenes TGA (RVA de 24 bits y 32 bits de RGBQ en color verdadero)
- Resolución máxima de textura de 2048x2048
- Un máximo de un mapa de difusión, un mapa normal y un mapa de cubos de reflexión por malla
- El canal alfa en texturas difusas hace que los píxeles se descartan si se muestra debajo 50%

### Animación

- Animación de escalar/rotar/traslación en objetos individuales
- Animación esquemática (RIGGED) con la piel
  - Máximo de 4 influencias por vértice

### Materiales

- Se admiten materiales Lambert y Phong con parámetros ajustables.
- Propiedades de material compatible con Lambert
  - Textura principal (prueba RGB + Alpha)
  - Color difuso (RGB)
  - Color ambiente (RGB)
- Propiedades de material admitidas para Phong
  - Textura principal (prueba RGB + Alpha)
  - Color difuso (RGB)
  - Color ambiente (RGB)
  - Color especular (RGB)
  - Brillo
  - Reflexión
- No se admiten materiales personalizados
- El máximo de un material por malla
- El máximo de una capa de material
- Máximo de 8 materiales por archivo

### Limitaciones de archivos y modelos

Hay unos claros límites para el tamaño de los archivos y para el número de modelos, vértices y mallas que pueden abrirse de forma simultánea en la versión beta del visor 3D:

- 500 MB de tamaño máximo de archivo por modelo
- Vértices: 600 000 combinados con todos los modelos abiertos
- Mallas: 1 600 combinadas en todos los modelos abiertos
- El máximo de 40 modelos abiertos al mismo tiempo

## Optimización de modelos 3D para la versión beta del visor 3D

### Consideraciones especiales

- Evitar los materiales negros o las áreas negras en los mapas de textura. Los hologramas están hechos de luz, por lo que HoloLens hace que el negro (la ausencia de luz) sea transparente.
- Antes de exportar a FBX desde su herramienta de creación, asegúrese de que toda la geometría sea visible y está desbloqueada y que ninguna de las capas que contienen la geometría esté desactivada o con plantilla. No se respeta la visibilidad.
- Evitar desplazamientos de traducción muy grandes entre nodos (por ejemplo, 100 000 unidades). Esto puede hacer que el modelo se rote mientras se mueve o se escala/gira.

### Optimización del rendimiento

Tenga en cuenta el rendimiento siempre que crees contenido y valides en la aplicación de la versión beta del visor 3D en HoloLens durante el proceso de creación para obtener los mejores resultados. La versión beta del visor 3D representa el contenido en tiempo real y el rendimiento depende de las capacidades del hardware de HoloLens.  

Hay muchas variables en un modelo 3D que pueden afectar al rendimiento. La versión beta del visor 3D mostrará una advertencia durante la carga cuando haya más de 150 000 vértices o más de 400 mallas. Las animaciones pueden afectar al rendimiento de otros modelos abiertos. También hay unos límites claros en el número total de modelos, vértices y mallas que pueden abrirse de forma simultánea en la versión beta del visor 3D (consulte [Limitaciones de archivos y modelos](#file-and-model-limitations)).  

Si el modelo 3D no se ejecuta bien debido a la complejidad del modelo, considere:

- Reducir el número de polígonos
- Reducir el número de huesos en la animación rigged
- Evitar la auto-oclusión

La versión beta del visor 3D admite la representación a doble cara, aunque está desactivada de manera predeterminada por motivos de rendimiento. Esto se puede activar a través del botón **Doble cara** en la página **Detalles**. Para obtener un rendimiento óptimo, evite tener que representar a doble cara en su contenido.

### Validar su modelo 3D

Para validar su modelo, ábralo en la versión beta del visor 3D en HoloLens. Seleccione el botón **Detalles** para ver las características de su modelo y las advertencias de contenido no compatible (si lo hay).

### Representación de modelos 3D con dimensiones reales

De forma predeterminada, la versión beta del visor 3D muestra modelos 3D con un tamaño y una posición cómodos para el usuario. Sin embargo, si el procesamiento de un modelo 3D con las medidas reales es importante (por ejemplo, al evaluar los modelos de mobiliario en una sala), el creador del contenido puede establecer un marcador en los metadatos del archivo para evitar el cambio de tamaño del modelo tanto por la aplicación como por el usuario.

Para evitar la escala del modelo, agregue un atributo personalizado de tipo booleano a cualquier objeto de la escena denominada Microsoft_DisableScale y establézcalo como true. La versión beta del visor 3D respetará la información de FbxSystemUnit incorporada en el archivo FBX. La escala en la versión beta del visor 3D es de un metro por cada unidad FBX.

## Ver archivos FBX en HoloLens

### Abrir un archivo FBX desde Microsoft Edge

Los archivos FBX pueden abrirse directamente desde un sitio web con Microsoft Edge en HoloLens.

1. En Microsoft Edge, navegue hasta la página web que contenga el archivo FBX que quiera ver.
1. Seleccione el archivo para descargarlo.
1. Cuando termine la descarga, seleccione el botón **Abrir** en Microsoft Edge para abrir el archivo en la versión beta del visor 3D.

Se puede acceder al archivo descargado y volver a abrirlo más tarde utilizando Descargas en Microsoft Edge. Para guardar un modelo 3D y asegurar el acceso continuo, descargue el archivo en el equipo y guárdelo en su cuenta de OneDrive. El archivo se puede abrir desde la aplicación de OneDrive en HoloLens.

> [!NOTE]
> Algunos sitios web con modelos de FBX descargables los proporcionan en formato comprimido ZIP. La versión beta del visor 3D no puede abrir archivos ZIP directamente. En su lugar, use su PC para extraer el archivo FBX y guardarlo en su cuenta de OneDrive. El archivo se puede abrir desde la aplicación de OneDrive en HoloLens.

### Abrir un archivo FBX desde OneDrive

Los archivos FBX se pueden abrir desde OneDrive con la aplicación de OneDrive en HoloLens. Asegúrese de que ha instalado OneDrive usando la aplicación de Microsoft Store en HoloLens y que ya ha subido el archivo FBX a OneDrive en su PC.

Una vez en OneDrive, puede que los archivos FBX se abran en HoloLens con la versión beta del visor 3D usando uno de los dos siguientes métodos:

- Inicie OneDrive en HoloLens y seleccione el archivo FBX para abrirlo en la versión beta del visor 3D.
- Inicie la versión beta del visor 3D, pulse la pantalla para mostrar la barra de herramientas, y seleccione **Abrir archivo**. Se iniciará OneDrive, lo que le permitirá seleccionar un archivo FBX.

## Solución de problemas

### Aparecen advertencias al abrir un modelo 3D

Verá una advertencia si intenta abrir un modelo 3D que contiene características que no son compatibles con la versión beta del visor 3D, o si el modelo es demasiado complejo y el rendimiento puede verse afectado. La versión beta del visor 3D seguirá cargando el modelo 3D, pero el rendimiento o la fidelidad visual podrían verse comprometidos.

Para obtener más información, vea [Especificaciones de contenido compatibles](#supported-content-specifications) y [Optimizar modelos 3D para la versión beta del visor 3D](#optimizing-3d-models-for-3d-viewer-beta).

### Veo una advertencia y el modelo 3D no se carga.

Verá un mensaje de error cuando la versión beta del visor 3D no pueda cargar un modelo 3D debido a la complejidad o al tamaño del archivo, o si el archivo FBX está corrupto o no es válido. También verá un mensaje de error si se ha alcanzado el límite en el número total de modelos, vértices o mallas que pueden abrirse simultáneamente.  

Para obtener más información, vea [Especificaciones de contenido compatibles](#supported-content-specifications) y [Limitaciones de archivo y modelo](#file-and-model-limitations).

### El modelo 3D se carga, pero no se muestra como se esperaba

Si el modelo 3D no se ve de la forma esperada en la versión beta del visor 3D, pulse para mostrar la barra de herramientas y, a continuación, seleccione **Detalles**. Los aspectos del archivo que no se admiten en la versión beta del visor 3D se resaltarán como advertencias.

El problema más común que podría ver es que faltan las texturas, probablemente ya no se incrusten en el archivo FBX. En este caso, el modelo se mostrará blanco. Este problema se puede solucionar en el proceso de creación al exportar desde la herramienta de creación a FBX con la opción incrustar texturas seleccionada.

Para obtener más información, vea [Especificaciones de contenido compatibles](#supported-content-specifications) y [Optimizar modelos 3D para la versión beta del visor 3D](#optimizing-3d-models-for-3d-viewer-beta).

### Experimente caídas de rendimiento mientras visualiza el modelo 3D

El rendimiento al cargar y ver un modelo 3D puede verse afectado por la complejidad del modelo, el número de modelos abiertos simultáneamente o el número de modelos con animaciones activas.

Para obtener más información, vea [Optimización de modelos 3D para la versión beta del Visor 3D](#optimizing-3d-models-for-3d-viewer-beta) y [ Limitaciones de archivos y modelos](#file-and-model-limitations).

### Al abrir un archivo de FBX en HoloLens, no se abre en la versión beta del visor 3D

La versión beta del visor 3D se asocia automáticamente a la extensión de archivo. FBX cuando se instala.

Si intenta abrir un archivo de FBX y ve un cuadro de diálogo que le dirige a Microsoft Store, en este momento no tiene ninguna aplicación asociada con la extensión de archivo. FBX en HoloLens.

Compruebe que la versión beta del visor 3D está instalado. Si no está instalado, descárguelo desde Microsoft Store en HoloLens.

Si la versión beta del visor 3D ya está instalado, iníciela y, a continuación, vuelva a abrir el archivo. Si el problema persiste, desinstale y vuelva a instalar la versión beta del visor 3D. Se volverá a asociar la extensión de archivo FBX con la versión beta del visor 3D.

Si al intentar abrir un archivo de FBX se abre una aplicación que no es la versión beta del visor 3D, es probable que esa aplicación se instale después de la versión beta del visor 3D y que haya asumido la asociación con la extensión de archivo FBX. Desinstale y vuelva a instalar la versión beta del visor 3D si prefiere que esta esté asociada con la extensión de archivo FBX.

### El botón Abrir archivo de la versión beta del visor 3D no inicia ninguna aplicación

El botón **Abrir archivo** abrirá la aplicación asociada a la función del selector de archivos en HoloLens. Si OneDrive está instalado, el botón **Abrir archivo** debe iniciar OneDrive. Sin embargo, si no hay actualmente ninguna aplicación asociada a la función selector de archivos instalada en HoloLens, se le dirigirá a Microsoft Store.

Si el botón **Abrir archivo** inicia una aplicación que no sea OneDrive, es probable que esa aplicación se haya instalado después de OneDrive y haya asumido la asociación con la función del selector de archivos. Si prefiere que OneDrive se inicie cuando seleccione el botón **Abrir archivo** de la versión beta del visor 3D, desinstale y vuelva a instalar OneDrive.

Si el botón **Abrir archivo** no está activo, es posible que haya alcanzado el límite de modelos que se pueden abrir al mismo tiempo en la versión beta del visor 3D. Si tiene 40 modelos abiertos en la versión beta del visor 3D, tendrá que cerrar algunas antes de poder abrir más modelos.

## Recursos adicionales

- [Foros de soporte](http://forums.hololens.com/categories/3d-viewer-beta): Solo para archivar. Este foro ya no está activo.
- [AVISOS DE TERCEROS](https://www.microsoft.com/{lang-locale}/legal/products)
