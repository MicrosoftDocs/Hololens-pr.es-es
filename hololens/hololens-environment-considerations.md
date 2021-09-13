---
title: Consideraciones sobre el entorno de HoloLens
description: Consiga la mejor experiencia posible usando HoloLens al optimizar el dispositivo para los ojos y el entorno.
author: dorreneb
ms.author: dobrown
manager: jarrettr
ms.date: 8/29/2019
ms.prod: hololens
ms.topic: article
audience: ITPro
ms.localizationpriority: high
keywords: marco holográfico, campo de visión, calibración, espacios, entorno, procedimientos, HoloLens, realidad mixta, cascos de realidad mixta
ms.openlocfilehash: 6976527d759e768fa5da72f96395a8b7b390cefd
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2021
ms.locfileid: "126034520"
---
# <a name="hololens-environment-considerations"></a>Consideraciones sobre el entorno de HoloLens

HoloLens combina el mundo holográfico con el mundo "real", colocando hologramas en el entorno. Una ventana de la aplicación holográfica "cuelga" de la pared, una bailarina holográfica gira sobre la mesa y encima de la cabeza de un amigo aparecen orejas de conejo sin que se dé cuenta. Cuando se usa una aplicación o un juego inmersivo, el mundo holográfico se propaga para rellenar el entorno, pero todavía se podrá ver el espacio y desplazarse por él.

Los hologramas que se coloquen permanecerán donde se hayan colocado, incluso si se desactiva el dispositivo.

## <a name="setting-up-an-environment"></a>Configuración de un entorno

Los dispositivos de HoloLens saben cómo colocar hologramas estables y precisos mediante el *seguimiento* de los usuarios en un espacio. Sin un seguimiento adecuado, el dispositivo no comprende el entorno ni al usuario que se encuentra dentro de él. Los hologramas pueden aparecer en los lugares equivocados, no aparecer en el mismo lugar cada vez o no aparecer en absoluto. Los datos que se usan para realizar un seguimiento de los usuarios se representan en el *mapa espacial*.  

El rendimiento del seguimiento se ve muy influido por el entorno en el que se encuentra el usuario, y la optimización de un entorno para inducir un seguimiento estable y coherente es más un arte que una ciencia. Son muchos los diferentes factores del entorno que se combinan para permitir el seguimiento, pero como desarrollador de Mixed Reality, hay varios factores que puede tener en cuenta para optimizar un espacio y lograr así un mejor seguimiento.

### <a name="lighting"></a>Iluminación

Windows Mixed Reality usa la luz visible para hacer el seguimiento de la ubicación del usuario. Cuando un entorno es demasiado brillante, las cámaras se pueden saturar y no se ve nada. Si el entorno es demasiado oscuro, las cámaras no pueden recoger suficiente información y no se ve nada. La iluminación debe ser uniforme y lo suficientemente brillante como para que los humanos puedan ver sin esfuerzo, pero no tan brillante como para que cueste mirar a la luz.  

Las áreas en las que hay puntos de luz brillante en un área tenue general también son problemáticas, ya que la cámara debe ajustarse cuando se mueve dentro y fuera de espacios brillantes. Esto puede hacer que el dispositivo "se pierda" y que crea que el cambio en la luz equivale a un cambio en la ubicación. Los niveles de iluminación estables en una área mejorarán el seguimiento.  

Cualquier iluminación exterior también puede provocar inestabilidad en la herramienta de seguimiento, ya que el sol puede variar considerablemente con el tiempo. Por ejemplo, si se realiza un seguimiento en el mismo espacio en verano frente a invierno, se pueden producir resultados drásticamente diferentes, ya que la luz indirecta exterior puede estar más elevada en distintos momentos del año.  

Si dispone de un luxómetro, 500-1000 lux está bien para empezar.  

#### <a name="types-of-lighting"></a>Tipos de iluminación

Los diferentes tipos de luz de un espacio también pueden influir en el seguimiento. Las bombillas emiten pulsos con la electricidad de CA que pasa por ellas; si la frecuencia de CA es de 50 Hz, la luz emite pulsos a 50 Hz. Un humano no puede ver este pulso. Sin embargo, la cámara de 30 fps del dispositivo HoloLens ve estos cambios: algunos fotogramas estarán bien iluminados, otros estarán mal iluminados y algunos otros estarán sobreexpuestos a medida que la cámara intente compensar los pulsos de luz.  

En Estados Unidos, el estándar de frecuencia de electricidad es de 60 Hz, de modo que los pulsos de las bombillas se armonizan con la velocidad de fotogramas de HoloLens: los pulsos de 60 Hz se alinean con la velocidad de fotogramas de 30 fps de HoloLens. Sin embargo, muchos países tienen un estándar de frecuencia de CA de 50 Hz, lo que significa que algunos fotogramas de HoloLens se tomarán durante los pulsos y otros no. En concreto, se sabe que la iluminación fluorescente en Europa causa problemas.  

Puede probar varias opciones para resolver problemas de parpadeo. La temperatura, la antigüedad de la bombilla y los ciclos de calentamiento son causas habituales de parpadeo fluorescente y la sustitución de las bombillas puede resultar de utilidad. También puede ayudar apretar las bombillas y asegurarse de que los consumos de energía sean constantes.  

### <a name="items-in-a-space"></a>Elementos de un espacio

HoloLens usa puntos de referencia medioambientales únicos, también conocidos como *características*, para encontrarse en un espacio.  

Un dispositivo casi nunca puede realizar un seguimiento en un área con pocas características, ya que el dispositivo no tiene ninguna forma de saber dónde se encuentra en el espacio. Normalmente, la adición de características a las paredes de un espacio es una buena forma de mejorar el seguimiento. Los pósteres, símbolos adheridos a una pared, plantas, objetos únicos u otros elementos de ese tipo sirven de ayuda. Un escritorio desordenado es un buen ejemplo de un entorno que favorece un buen seguimiento: hay muchas características diferentes en una sola área.  

Use características únicas en el mismo espacio. Por ejemplo, el mismo póster repetido varias veces en una pared confundirá al dispositivo, ya que HoloLens no sabrá cuál de los pósteres está mirando. Una forma habitual de agregar características únicas es usar líneas de cinta adhesiva para crear patrones únicos y no repetitivos en las paredes y el suelo de un espacio.  

Una buena pregunta que se debe hacer es: si solo ha visto una pequeña parte de la escena, ¿se podría encontrar a sí mismo en el espacio? Si no es así, es probable que el dispositivo también tenga problemas para realizar el seguimiento.

#### <a name="wormholes"></a>Agujeros de gusano

Si hay dos áreas o regiones que tienen el mismo aspecto, es posible que la herramienta de seguimiento piense que son iguales. Esto hace que el dispositivo se confunda y piense que se encuentra en otro lugar. Llamamos a estos tipos de áreas repetitivas *agujeros de gusano*.  

Para evitar los agujeros de gusano, intente evitar áreas idénticas en el mismo espacio. Las áreas idénticas pueden incluir estaciones de una fábrica, ventanas de un edificio, racks de servidor o estaciones de trabajo. El etiquetado de áreas o la adición de características únicas a cada área con un aspecto similar pueden ayudar a reducir los agujeros de gusano.

### <a name="movement-in-a-space"></a>Movimiento en un espacio

Si el entorno se desplaza y cambia constantemente, el dispositivo no tiene características estables con respecto a las que encontrarse.  

Cuantos más objetos en movimiento haya en un espacio, incluidas las personas, más fácil será perder el seguimiento. Se sabe que las cintas transportadoras en movimiento, los elementos en diferentes estado de construcción y muchas personas en un espacio provocan problemas de seguimiento.

HoloLens puede adaptarse rápidamente a estos cambios, pero solo cuando esa área sea claramente visible para el dispositivo. Las áreas que no se ven con tanta frecuencia pueden tener un retraso con respecto a la realidad, lo que puede provocar errores en el mapa espacial. Por ejemplo, un usuario escanea a un amigo pero luego se da la vuelta cuando este sale de la habitación. En los datos del mapa espacial seguirá apareciendo una representación "fantasma" del amigo hasta que el usuario vuelva a examinar el espacio que ha quedado vacío.

### <a name="proximity-of-the-user-to-items-in-the-space"></a>Proximidad del usuario a los elementos del espacio

De forma similar a cómo los seres humanos no pueden centrarse bien en los objetos cercanos a los ojos, HoloLens tiene que esforzarse cuando los objetos están cerca de sus cámaras. Si un objeto se encuentra demasiado cerca como para poder verse con ambas cámaras, o si un objeto bloquea una cámara, el dispositivo tendrá muchos más problemas con el seguimiento del objeto.  

Las cámaras no pueden ver más cerca de 15 cm respecto a un objeto.

### <a name="surfaces-in-a-space"></a>Superficies en un espacio

Es probable que las superficies muy reflectantes tengan un aspecto diferente según el ángulo, lo que afecta al seguimiento. Piense en un coche nuevo: cuando se mueve alrededor de él, la luz se refleja y se van viendo diferentes objetos en la superficie. Para la herramienta de seguimiento, los diferentes objetos reflejados en la superficie representan un entorno cambiante, que provoca que el dispositivo pierda el seguimiento.

Es más fácil realizar un seguimiento de objetos menos brillantes.

### <a name="wi-fi-fingerprint-considerations"></a>Consideraciones de la huella digital de Wi-Fi

Siempre que esté habilitada la conexión Wi-Fi, los datos de mapa estarán correlacionados con una huella digital de Wi-Fi, incluso cuando no haya conexión con un enrutador o una red de Wi-Fi. Sin la información de Wi-Fi, puede resultar más lento reconocer el espacio y los hologramas. Si las señales de Wi-Fi cambian de forma significativa, es posible que el dispositivo piense que se encuentra en un espacio totalmente diferente.

La identificación de la red (como SSID o la dirección MAC) no se envía a Microsoft y todas las referencias de Wi-Fi se mantienen locales en HoloLens.

## <a name="mapping-new-spaces"></a>Mapa de nuevos espacios

Cuando acceda a un nuevo espacio (o cargue uno existente), verá un gráfico de malla extendiéndose sobre el espacio. Esto significa que el dispositivo está creando un mapa del entorno. Si bien un dispositivo HoloLens reconocerá un espacio con el tiempo, hay sugerencias y trucos para crear el mapa de los espacios.

## <a name="environment-management"></a>Administrador de entornos

Hay dos opciones de configuración que permiten a los usuarios "limpiar" los hologramas y hacer que HoloLens "olvide" un espacio. Se encuentran en **Holograms and environments** (Hologramas y entornos) en la aplicación de configuración, y la segunda opción también aparece en **Privacidad** en esa misma aplicación.  

1. **Delete nearby holograms** (Eliminar hologramas cercanos). Si selecciona esta opción, HoloLens borrará todos los hologramas anclados y todos los datos de mapa almacenados del "espacio actual" en el que se encuentra el dispositivo. Se creará una nueva sección de mapa de esa ubicación y se almacenará en la base de datos una vez que los hologramas se vuelvan a colocar en el mismo espacio.

1. **Delete all holograms** (Eliminar todos los hologramas). Si selecciona esta opción, HoloLens borrará TODOS los datos de mapa y los hologramas anclados en todas las bases de datos de espacios. No se volverán a detectar los hologramas y será necesario colocarlos de nuevo para que se vuelvan a almacenar secciones de mapas en la base de datos.

## <a name="hologram-quality"></a>Calidad del holograma

Los hologramas se pueden colocar en todo el entorno: por encima, por debajo y en cualquier lugar a su alrededor, pero los verá por medio de un [marco holográfico](/windows/mixed-reality/holographic-frame) que se encuentra delante de sus ojos. Para obtener la mejor vista, asegúrese de ajustar el dispositivo para que pueda ver todo el marco. Y no dude en recorrer el entorno y explorarlo.

Para que los [hologramas](/windows/mixed-reality/hologram) tengan un aspecto nítido, claro y estable, el dispositivo HoloLens debe estar calibrado solo para uno mismo. La primera vez que configure su HoloLens, se le guiará por este proceso. Más adelante, si los hologramas no tienen el aspecto adecuado o aparecen numerosos errores, podrá realizar ajustes.

Si tiene problemas para crear el mapa de los espacios, intente eliminar los hologramas cercanos y volver a crear el mapa.

### <a name="calibration"></a>Calibración

Si los hologramas parecen inestables o se mueven, o si tiene problemas para colocar hologramas, lo primero que se debe probar es la [aplicación de calibración](hololens-calibration.md). Esta aplicación también puede ayudar si se aprecian molestias al usar el dispositivo HoloLens.

Para llegar a la aplicación de calibración, vaya a **Configuración** > **Sistema** > **Utilidades**. Seleccione **Abrir calibración** y siga las instrucciones.

Si otra persona va a usar su dispositivo HoloLens, esa persona deberá ejecutar primero la aplicación de calibración para que el dispositivo se adapte correctamente a ella.

## <a name="temperature-and-regulatory-information"></a>Información de temperatura y normativas

[Información de normativas de Microsoft HoloLens](https://support.microsoft.com/en-us/help/13761/hololens-regulatory-information): incluye información sobre el intervalo de temperatura, la eliminación del producto, las interferencias de radio y televisión, etc.

Consulte los detalles de "HoloLens" en [Materiales y sustancias](https://www.microsoft.com/legal/compliance/materials-substances); consulte el artículo 33 sobre divulgación del cumplimiento medioambiental (PDF).

Estas son algunas directrices que debe seguir al usar el dispositivo:

1. Tenga el dispositivo en un entorno dentro del intervalo de temperatura (ya esté en modo de espera o apagado) durante una hora antes de usarlo.
1. Use el dispositivo en un entorno que esté dentro del intervalo de temperatura.
1. Use el dispositivo en interiores.
1. Use el dispositivo a la sombra; incluso en interior, evite la luz solar directa que entra por ventanas o claraboyas.
1. Si sigue las instrucciones anteriores pero surgen problemas inesperados de sobrecalentamiento, siga los pasos que se indican a continuación para enviar [comentarios](hololens-feedback.md). 
    1. Asegúrese de que está habilitada en el dispositivo la telemetría, ya sea **Completa** u **Opcional**. Si no lo está, habilítela. 
    >[!CAUTION]
    > La telemetría no es retroactiva para eventos térmicos: debe habilitarse durante el sobrecalentamiento o no se capturarán los datos necesarios.
    
    2. Reproduzca el problema de calentamiento.
    3. Incluya la fecha y hora en que se produjo el sobrecalentamiento.
    4. Envíe los [comentarios](hololens-feedback.md).

## <a name="see-also"></a>Vea también

- [Diseño de asignaciones espaciales](/windows/mixed-reality/spatial-mapping)
- [Hologramas](/windows/mixed-reality/hologram)
