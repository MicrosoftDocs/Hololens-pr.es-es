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
# Mapa de espacios físicos con HoloLens

HoloLens funde un holograma con su mundo físico. Para hacerlo, HoloLens tiene que obtener información sobre el mundo físico de su sitio web y recordar en qué lugar del espacio se colocan hologramas.

Con el tiempo, HoloLens crea un *mapa espacial* del entorno que ha visto.  HoloLens actualiza el mapa a medida que el entorno cambia. Siempre y cuando haya iniciado sesión y el dispositivo esté activado, HoloLens crea y actualiza sus mapas espaciales. Si mantiene o se lleva el dispositivo con las cámaras a las que señala un espacio, HoloLens intenta asignar el área. Mientras HoloLens aprende un espacio de forma natural a lo largo del tiempo, hay varias maneras en las que HoloLens le ayuda a la hora de diseñar su espacio de manera más rápida y eficaz.  

> [!NOTE]
> Si su HoloLens no puede mapear su espacio o está fuera de calibración, el HoloLens puede entrar en modo limitado. En el modo limitado, no podrá colocar hologramas en su entorno.

Este artículo explica cómo HoloLens asigna espacios, cómo mejorar la asignación espacial y cómo administrar los datos espaciales que recopila.

## Elección y configuración de su espacio

Las características de su entorno pueden dificultar que HoloLens interprete un espacio. Los niveles de luz, los materiales en el espacio, el diseño de los objetos y otros pueden afectar a la forma en que HoloLens asigna un área.

HoloLens funciona mejor en ciertos tipos de entornos. Para crear el mejor mapa de espacios espaciales, elija una sala que tenga la luz adecuada y disponga de suficiente espacio. Evite espacios en blanco y negro en oscuro que contengan una gran cantidad de superficie oscura, brillante o traslúcida (por ejemplo, espejos o cortinas gauzy).

HoloLens está optimizado para el uso en interiores. La asignación espacial también funciona mejor cuando se enciende Wi-Fi, aunque no es necesario conectarse a una red. HoloLens puede obtener puntos de acceso Wi-Fi incluso si no está conectado o autenticado. La funcionalidad de HoloLens no cambia si los puntos de acceso se conectan a través de Internet o de forma local o intranet.

Solo use HoloLens en lugares seguros sin peligro. [Más sobre la seguridad](https://support.microsoft.com/help/4023454/safety-information).

## Asignación de espacio

Ya está listo para empezar a asignar el spare.  Cuando HoloLens inicia la asignación de un entorno, verá un gráfico de la malla que se propaga por el espacio.  En la página principal de la realidad mixta, puede activar el mapa que se muestra al seleccionar en una superficie asignada.

Aquí encontrará directrices para crear un magnífico mapa espacial.

### Entender los escenarios para el área

Es importante gastar el tiempo necesario para usar HoloLens, por lo que la equivalencia es relevante y completa. Por ejemplo, si un escenario de usuario para HoloLens implica moverse de un punto a otro en el punto B, desplácese por la ruta de dos a tres ocasiones y busque en todas las direcciones a medida que se desplace.  

### Recorra lentamente alrededor del espacio

Si se dirige demasiado rápido en torno al área, es probable que HoloLens se quede con errores de asignación de áreas. Recorra lentamente alrededor del espacio y, a continuación, detenga cada 5 a 8 pies para buscar en todo el entorno.  

Los movimientos suaves también ayudan a la asignación de HoloLens de forma más eficaz.

### Buscar en todas las direcciones

La búsqueda a medida que se asigna el espacio les proporciona más información sobre los puntos que están relacionados entre sí.  

Si no lo hace, es posible que HoloLens no pueda averiguar el lugar en el que se encuentra el techo en la habitación.  

No olvide tener que buscar en el piso cuando asigne el espacio.

### Cubrir las áreas clave varias veces

Desplazarse por un área varias veces ayudará a recoger las características que es posible que falten en el primer tutorial. Para crear un mapa ideal, pruebe a resaltar un área de dos a tres veces.

Si es posible, al repetir estos movimientos, pase el tiempo pasando por un área en una dirección y, después, vuelva a la parte posterior y, a continuación, vuelva a desplazarse a la forma en que llegó.

### Llevar la hora asignada al área

Puede tardar entre 15 y 20 minutos en que HoloLens se asigne completamente y se ajuste a su entorno. Si tiene un espacio en el que tiene previsto usar HoloLens con frecuencia, al dedicar ese tiempo al espacio para asignar el espacio, se pueden evitar los problemas más adelante.  

## Posibles errores en el mapa espacial

Los errores en los datos de asignación espacial se dividen en algunas categorías:

- *Orificios*: no se muestran las superficies del mundo real en los datos de la asignación espacial.
- *Hallucinations*: existen superficies en los datos de asignación espacial que no existen en el mundo real.
- *Túneles espaciales*: HoloLens "pierde" parte del mapa espacial pensando en que se encuentra en otra parte del mapa que realmente es.
- *Bias*: las superficies en los datos de la asignación espacial se alinean de forma imperfecta con las superficies del mundo real, ya sea insertadas o extraídas.

Si ve alguno de estos errores, utilice el [FeedbackHub](hololens-feedback.md) para enviar comentarios.

## Seguridad y almacenamiento para datos espaciales

La actualización de la versión 1803 de Windows 10 para Microsoft HoloLens y posterior almacena datos de asignación en una base de datos local (en el dispositivo).

Los usuarios de HoloLens no pueden acceder a la base de datos de mapas directamente, incluso si el dispositivo está conectado a un equipo PC o al usar la aplicación del explorador de archivos. Cuando se habilita BitLocker en HoloLens, los datos de mapa almacenados también se cifran junto con todo el volumen.

### Quitar los datos de mapa y los espacios conocidos de HoloLens

Hay dos opciones para eliminar datos de mapa en la **Configuración> > hologramas del sistema**:

- Para eliminar el holograma cerca, seleccione **Quitar hologramas próximos**. Este comando borra los datos de mapa y los hologramas anclados del espacio actual. Si continúa utilizando el dispositivo en el mismo espacio, se crea y se almacena una sección de mapa completamente nuevo para reemplazar la información eliminada.

   > [!NOTE]
   > Los hologramas "Cercanos" son hologramas que están anclados en la misma sección de mapa en el espacio actual.

   Por ejemplo, puede usar esta opción para borrar los datos de mapa relacionados con el trabajo sin afectar a los datos de mapa relacionados con el hogar.

- Para eliminar todos los hologramas, seleccione **Quitar todos los hologramas**. Este comando borra todos los datos de mapa almacenados en el dispositivo, así como todos los hologramas delimitados. Tendrá que realizar explícitamente un holograma. No podrá volver a detectar los hologramas que colocó anteriormente.

> [!NOTE]
> Después de quitar los hologramas o cercanos, HoloLens inicia inmediatamente el examen y la asignación del espacio actual.

### Datos de redes Wi-Fi en mapas espaciales

HoloLens almacena características Wi-Fi para ayudarle a correlacionar las ubicaciones de hologramas y las secciones de mapa que se almacenan en la base de datos HoloLens de espacios conocidos. La información sobre las características de Wi-Fi no es accesible para los usuarios y no se envía a Microsoft a través de la nube o mediante telemetría.

Siempre y cuando se habilite Wi-Fi, HoloLens correlaciona los datos de mapa con puntos de acceso Wi-Fi cercanos. No hay ninguna diferencia en el comportamiento tanto si una red está conectada como si solo se detecta cerca. Si Wi-Fi está deshabilitado, HoloLens continúa buscando en el espacio. Sin embargo, HoloLens tiene que buscar más datos de mapas en la base de datos Spaces y es posible que necesite más tiempo para encontrar hologramas. En ausencia de la información de Wi-Fi, HoloLens tiene que comparar las exploraciones activas con todos los anclajes de hologramas y las secciones de mapa que se almacenan en el dispositivo para localizar la parte correcta del mapa.

## Temas relacionados

- [Diseño de mapas espaciales](https://docs.microsoft.com/windows/mixed-reality/spatial-mapping-design)
