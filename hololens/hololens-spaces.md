---
title: Mapa de espacios físicos con HoloLens
description: HoloLens aprende el aspecto que tiene un espacio con el tiempo. Los usuarios pueden facilitar este proceso moviendo las HoloLens de determinadas maneras por el espacio.
ms.assetid: bd55ecd1-697a-4b09-8274-48d1499fcb0b
author: dorreneb
ms.author: dobrown
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.date: 09/16/2019
keywords: hololens, Windows Mixed Reality, diseño, mapa espacial, HoloLens, reconstrucción superficial, malla, seguimiento de la cabeza, mapas
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 1 (1st gen)
- HoloLens 2
ms.openlocfilehash: d1eef6bdf463aa400504af7b35a0fd2b8e2b44499d6ff7b93e70a2dd5952ef88
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "115662849"
---
# <a name="map-physical-spaces-with-hololens"></a>Mapa de espacios físicos con HoloLens

HoloLens combina hologramas con su mundo físico. Para hacerlo, HoloLens tiene que obtener información sobre el mundo físico que lo rodea y recordar en qué lugar del espacio deben colocarse los hologramas.

Con el tiempo, HoloLens crea un *mapa espacial* del entorno que ha visto.  HoloLens actualiza el mapa a medida que el entorno cambia. Siempre y cuando haya iniciado sesión y el dispositivo esté encendido, HoloLens crea y actualiza sus mapas espaciales. Si sujeta o se pone el dispositivo con las cámaras señalando un espacio, HoloLens intenta crear un mapa del área. Mientras HoloLens aprende un espacio de forma natural con el tiempo, tiene varias maneras de ayudar a HoloLens a crear un mapa del espacio de manera más rápida y eficaz.  

> [!NOTE]
> Si su HoloLens no puede crear un mapa del espacio o no está calibrado, es posible que entre en modo limitado. En el modo limitado, no podrá colocar hologramas en su entorno.

En este artículo se explica cómo HoloLens crea mapas de espacios, cómo mejorar los mapas espaciales y cómo administrar los datos espaciales que HoloLens recopila.

## <a name="choosing-and-setting-up-and-your-space"></a>Elección y configuración del espacio

Las características del entorno pueden dificultar que HoloLens interprete un espacio. Los niveles de luz, los materiales del espacio, la disposición de los objetos y otros aspectos pueden afectar a la forma en que HoloLens crea un mapa de un área.

HoloLens funciona mejor en ciertos tipos de entornos. Para crear el mejor mapa espacial, elija una sala que tenga la luz adecuada y espacio suficiente. Evite espacios oscuros y salas con muchas superficies oscuras, brillantes o traslúcidas (por ejemplo, espejos o cortinas diáfanas).

HoloLens está optimizado para el uso en interiores. Los mapas espaciales también funcionan mejor cuando se activa la Wi-Fi, aunque no es necesario conectarse a una red. HoloLens puede obtener puntos de acceso Wi-Fi aunque no esté conectado o autenticado. La funcionalidad de HoloLens no cambia si los puntos de acceso están conectados a Internet o solo a la intranet o localmente.

Solo use HoloLens en lugares seguros sin riesgos. [Más información sobre la seguridad](https://support.microsoft.com/help/4023454/safety-information).

## <a name="mapping-your-space"></a>Creación de un mapa del espacio

Ya está listo para empezar a crear un mapa de su espacio.  Cuando HoloLens inicia la creación de un mapa del entorno, se muestra un gráfico de malla que se propaga por el espacio.  En el ambiente principal, puede activar el mapa que debe mostrarse si selecciona una superficie del mapa.

Aquí encontrará directrices para crear un magnífico mapa espacial.

### <a name="understand-the-scenarios-for-the-area"></a>Comprensión de los escenarios del área

Es importante dedicar la mayor parte del tiempo a usar el HoloLens, para que el mapa sea pertinente y esté completo. Por ejemplo, si un escenario de usuario para HoloLens implica moverse del punto A al punto B, recorra el camino dos o tres veces, mirando en todas direcciones mientras se desplaza.  

### <a name="walk-slowly-around-the-space"></a>Caminar lentamente por el espacio

Si camina demasiado rápido por el área, es probable que HoloLens no incluya algunas áreas en el mapa. Recorra lentamente el espacio y deténgase cada 1 a 3 metros para mirar todo el entorno.  

Los movimientos suaves también ayudan a HoloLens a crear mapas de forma más eficaz.

### <a name="look-in-all-directions"></a>Mirar en todas direcciones

Al mirar el entorno mientras se crea el mapa, el espacio proporciona más información a HoloLens sobre los puntos que están relacionados entre sí.  

Si no lo hace, es posible que HoloLens no pueda averiguar dónde está el techo de la sala.  

No olvide mirar al suelo cuando cree el mapa del espacio.

### <a name="cover-key-areas-multiple-times"></a>Cubrir áreas clave varias veces

Si se desplaza por un área varias veces ayudará a captar las características que puedan haberse omitido en el primer recorrido. Para crear un mapa ideal, pruebe a recorrer un área de dos a tres veces.

Si es posible, al repetir estos movimientos, recorra un área en una dirección y, después, haga el mismo camino en sentido contrario.

### <a name="take-your-time-mapping-the-area"></a>Dedicar tiempo para crear un mapa del área

HoloLens puede necesitar entre 15 y 20 minutos para crear el mapa completo y adaptarse al entorno. Si tiene un espacio en el que tiene previsto usar HoloLens con frecuencia, dedique tiempo a crear el mapa del espacio para evitar problemas más adelante.  

## <a name="possible-errors-in-the-spatial-map"></a>Posibles errores en el mapa espacial

Los errores en los datos del mapa espacial se clasifican en algunas categorías:

- *Agujeros*: las  superficies reales carecen de datos de mapas espaciales.
- *Alucinaciones*: existen superficies en los datos de mapas espacial que no existen en el mundo real.
- *Agujeros espaciotemporales*: HoloLens "pierde" parte del mapa espacial y piensa que se encuentra en otra parte del mapa distinta de la real.
- *Sesgo*: las superficies de los datos del mapa espacial se alinean de forma imperfecta con las superficies reales, ya sea insertadas o extraídas.

Si ve alguno de estos errores, utilice el [Centro de opiniones](hololens-feedback.md) para enviar comentarios.

## <a name="security-and-storage-for-spatial-data"></a>Seguridad y almacenamiento de datos espaciales

La actualización de la versión 1803 de Windows 10 para Microsoft HoloLens y posteriores almacena datos de mapas en una base de datos local (en el dispositivo).

Los usuarios de HoloLens no pueden acceder a la base de datos de mapa directamente, aunque el dispositivo esté conectado a un equipo o se use la aplicación Explorador de archivos. Cuando se habilita BitLocker en HoloLens, los datos de mapa almacenados también se cifran junto con todo el volumen.

### <a name="remove-map-data-and-known-spaces-from-hololens"></a>Quitar los datos de mapa y espacios conocidos de HoloLens

Hay dos opciones para eliminar datos de mapa en **Configuración > Sistema > Hologramas**:

- Para eliminar hologramas cercanos, seleccione **Quitar hologramas cercanos**. Este comando borra los datos de mapa y los hologramas anclados del espacio actual. Si continúa utilizando el dispositivo en el mismo espacio, se crea y se almacena una sección de mapa completamente nueva para reemplazar la información eliminada.

   > [!NOTE]
   > Los hologramas "Cercanos" son hologramas que están anclados en la misma sección de mapa en el espacio actual.

   Por ejemplo, puede usar esta opción para borrar los datos de mapa relacionados con el trabajo sin que ello afecte a los datos de mapa relacionados con el hogar.

- Para eliminar todos los hologramas, seleccione **Quitar todos los hologramas**. Este comando borra todos los datos de mapa almacenados en el dispositivo, así como todos los hologramas anclados. Tendrá que colocar explícitamente los hologramas. No podrá volver a detectar los hologramas que colocó anteriormente.

> [!NOTE]
> Después de quitar todos los hologramas o los cercanos, HoloLens comienza inmediatamente la exploración y la creación del mapa del espacio actual.

### <a name="wi-fi-data-in-spatial-maps"></a>Datos de redes Wi-Fi en mapas espaciales

HoloLens almacena características Wi-Fi para ayudarle a correlacionar las ubicaciones de hologramas y las secciones de mapa que se almacenan en la base de datos de espacios conocidos de HoloLens. La información sobre las características de la red Wi-Fi no es accesible para los usuarios y no se envía a Microsoft a través de la nube ni mediante telemetría.

Siempre y cuando se habilite la red Wi-Fi, HoloLens correlaciona los datos de mapa con puntos de acceso Wi-Fi cercanos. No hay ninguna diferencia en el comportamiento tanto si una red está conectada como si solo se detecta cerca. Si la red Wi-Fi está deshabilitada, HoloLens continúa buscando en el espacio. Sin embargo, HoloLens tiene que buscar más datos de mapa en la base de datos de espacios y es posible que necesite más tiempo para buscar hologramas. En ausencia de la información de Wi-Fi, HoloLens tiene que comparar las exploraciones activas con todos los anclajes de hologramas y las secciones de mapa que se almacenan en el dispositivo para localizar la parte correcta del mapa.

## <a name="related-topics"></a>Temas relacionados

- [Diseño de asignaciones espaciales](/windows/mixed-reality/spatial-mapping)
