---
title: Consideraciones de entorno de HoloLens
description: Consigue la mejor experiencia posible usando HoloLens al optimizar el dispositivo para los ojos y el entorno. Muchos factores de entorno diferentes se fusionan para habilitar el seguimiento, pero como desarrollador de realidad mixta, hay varios factores que puedes tener en cuenta para optimizar un espacio para lograr mejores hologramas.
keywords: marco holográfico, campo de visión, fov, calibración, espacios, entorno, procedimientos
author: dorreneb
ms.author: dobrown
manager: jarrettr
ms.date: 8/29/2019
ms.prod: hololens
ms.topic: article
audience: ITPro
ms.localizationpriority: high
ms.openlocfilehash: 0fa147eb2b1194dacdcabff4995f5141a1b25bde
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857858"
---
# Consideraciones de entorno de HoloLens

HoloLens combina el mundo holográfico con el mundo "real", colocando hologramas en tu entorno. Una ventana de la aplicación holográfica "queda colgada" en la pared, una bailarina holográfica gira sobre la mesa, orejas de conejo aparecen encima de la cabeza de un amigo sin que él se dé cuenta. Si usas una aplicación o un juego inmersivo, el mundo holográfico se propagará para rellenar todo tu mundo, pero aún podrás ver el espacio y desplazarte por él.

Los hologramas que coloques permanecerán donde los hayas colocado, incluso si desactivas el dispositivo.

## Configuración de un entorno

Los dispositivos de HoloLens saben cómo colocar hologramas estables y precisos al *realizar un seguimiento* de los usuarios en un espacio. Sin un seguimiento adecuado, el dispositivo no comprende el entorno ni el usuario que se encuentra dentro, de modo que los hologramas pueden aparecer en los lugares equivocados, no aparecer en el mismo lugar cada vez o no aparecer en absoluto. Los datos que se usan para realizar un seguimiento de los usuarios se representan en el *mapa espacial*.  

El seguimiento del rendimiento se ve muy influido por el entorno en el que se encuentra el usuario y la optimización de un entorno para inducir un seguimiento estable y coherente es un arte en lugar de una ciencia. Muchos factores de entorno diferentes se fusionan para habilitar el seguimiento, pero como desarrollador de realidad mixta, hay varios factores que puedes tener en cuenta para optimizar un espacio para lograr un mejor seguimiento.

### Iluminación

Windows Mixed Reality usa la luz visible para realizar un seguimiento de la ubicación del usuario. Cuando un entorno es demasiado brillante, las cámaras se pueden saturar y no se ve nada. Si el entorno es demasiado oscuro, las cámaras no pueden recoger suficiente información y no se ve nada. La iluminación debe ser uniforme y lo suficientemente brillante como para que los humanos puedan ver sin esfuerzo, pero no tan brillante como para que cueste mirar a la luz.  

Las áreas en las que hay puntos de luz brillante en un área tenue general también son problemáticas, ya que la cámara debe ajustarse cuando se mueve dentro y fuera de espacios brillantes. Esto puede hacer que el dispositivo "se pierda" y que se cree que el cambio en la luz equivale a un cambio en la ubicación. Los niveles de iluminación estables en una área mejorarán el seguimiento.  

Cualquier iluminación exterior también puede provocar inestabilidad en la herramienta de seguimiento, ya que el sol puede variar considerablemente con el tiempo. Por ejemplo, si se realiza un seguimiento en el mismo espacio en verano frente a invierno, se pueden producir resultados drásticamente diferentes, ya que la luz indirecta exterior puede estar más elevada en distintos momentos del año.  

Si dispones de un luxómetro, 500-1000 lux está bien para empezar.  

#### Tipos de iluminación

Los diferentes tipos de luz en un espacio también pueden influir en el seguimiento. Las bombillas pulsan con la electricidad que pasa por ellas; si la frecuencia de CA es de 50Hz, la luz se pulsa a 50Hz. Un humano no puede ver este pulso. Sin embargo, la cámara de 30fps de HoloLens ve estos cambios: algunos fotogramas estarán bien iluminados, algunos estarán mal iluminados y otros estarán sobreexpuestos a medida que la cámara intente compensar los pulsos de luz.  

En Estados Unidos, el estándar de frecuencia de electricidad es de 60Hz, de modo que los pulsos de las bombillas se armonizan con la frecuencia de fotograma de HoloLens: los pulsos de 60HZ se alinean con la frecuencia de fotograma de 30fps de HoloLens. Sin embargo, muchos países tienen un estándar de frecuencia de CA de 50Hz, lo que significa que algunos fotogramas de HoloLens se tomarán durante los pulsos y otros no. En particular, se sabe que la iluminación fluorescente en Europa causa problemas.  

Puedes probar varias cosas para resolver problemas de parpadeo. La temperatura, la antigüedad de la bombilla y los ciclos de calentamiento son causas habituales de parpadeo fluorescente y la sustitución de las bombillas puede resultar de utilidad. Puede resultar de utilidad apretar las bombillas y asegurarse de que los consumos de energía sean constantes.  

### Elementos de un espacio

HoloLens usa puntos de referencia medioambientales únicos, también conocidos como *características*, para encontrarse en un espacio.  

Un dispositivo casi nunca puede realizar un seguimiento en un área sin características, ya que el dispositivo no tiene ninguna forma de saber dónde se encuentra en el espacio. Normalmente, la adición de características a las paredes de un espacio es una buena forma de mejorar el seguimiento. Los pósteres, símbolos adheridos a una pared, plantas, objetos únicos u otros elementos similares, todos ellos son de utilidad. Un escritorio desordenado es un buen ejemplo de un entorno que favorece un buen seguimiento: hay muchas características diferentes en una sola área.  

Además, usa características únicas en el mismo espacio. Por ejemplo, el mismo póster repetido varias veces en una pared confundirá al dispositivo, ya que HoloLens no sabrá a cuál de los pósteres está mirando. Una forma habitual de agregar características únicas es usar líneas de cinta adhesiva para crear patrones únicos y no repetitivos en las paredes y el suelo de un espacio.  

Una buena pregunta que te debes hacer es: si solo has visto una pequeña cantidad de la escena, ¿podrías encontrarte a ti mismo en el espacio? Si no es así, es probable que el dispositivo tenga problemas para realizar el seguimiento.

#### Agujeros de gusano

Si tienes dos áreas o regiones que tienen el mismo aspecto, es posible que el rastreador piense que son iguales. Esto hace que el dispositivo se confunda y piense que se encuentra en otro lugar. Llamamos a estos tipos de áreas repetitivas *agujeros de gusano*.  

Para evitar agujeros de gusano, intenta evitar áreas idénticas en el mismo espacio. Las áreas idénticas pueden incluir a veces emisoras de fábrica, ventanas de un edificio, racks de servidor o estaciones de trabajo. Las áreas de etiquetado o la adición de características únicas a cada área de aspecto similar pueden ayudar a mitigar los agujeros de gusano.

### Movimiento en un espacio

Si el entorno se desplaza y cambia constantemente, el dispositivo no tiene características estables con respecto a las que encontrarse.  

Cuanto más objetos móviles haya en un espacio, incluidas personas, más sencillo será perder el seguimiento. Se sabe que las cintas transportadoras en movimiento, los elementos en diferentes estado de construcción y muchas personas en un espacio provocan problemas de seguimiento.

HoloLens puede adaptarse rápidamente a estos cambios, pero solo cuando esa área sea claramente visible para el dispositivo. Las áreas que no se ven con tanta frecuencia pueden ir por detrás de la realidad, lo que puede provocar errores en el mapa espacial. Por ejemplo, un usuario digitaliza a un amigo y luego se da la vuelta cuando sale de la habitación. Una representación "fantasma" del amigo permanecerá en los datos de mapa espaciales hasta que el usuario vuelva a examinar el espacio que está vacío ahora.

### Proximidad del usuario a los elementos del espacio

De forma similar a cómo los seres humanos no pueden centrarse bien en los objetos cercanos a los ojos, HoloLens se esfuerza cuando los objetos están cerca de sus cámaras. Si un objeto se encuentra demasiado cerca para verse con ambas cámaras, o si un objeto bloquea una cámara, el dispositivo tendrá muchos más problemas con el seguimiento respecto al objeto.  

Las cámaras no pueden verse más cerca de 15cm desde un objeto.

### Superficies en un espacio

Las superficies muy reflectantes tengan un aspecto diferente según el ángulo, que afecta al seguimiento. Piensa en un coche completamente nuevo: cuando te muevas alrededor de él, se reflejará la luz y verás objetos diferentes en la superficie mientras te mueves. Para la herramienta de seguimiento, los diferentes objetos reflejados en la superficie representan un entorno cambiante y el dispositivo pierde el seguimiento.

Es más fácil realizar un seguimiento respecto a los objetos menos brillantes.

### Consideraciones de huella digital de Wi-Fi

Siempre que esté habilitada la conexión Wi-Fi, los datos de mapa estarán correlacionados con una huella digital de Wi-Fi, incluso cuando no estén conectados a un enrutador o una red de Wi-Fi. Sin la información de Wi-Fi, puede resultar más lento reconocer el espacio y los hologramas. Si las señales Wi-Fi cambian de forma significativa, es posible que el dispositivo piense que se encuentra en un espacio totalmente diferente.

La identificación de la red (como SSID o dirección MAC) no se envía a Microsoft y todas las referencias de Wi-Fi se mantienen locales en el HoloLens.

## Mapas de espacios nuevos

Cuando introduzcas un espacio nuevo (o cargues uno existente), verás un gráfico de malla extendiéndose sobre el espacio. Esto significa que el dispositivo se está asignando a tu entorno. Si bien un HoloLens reconocerá un espacio con el tiempo, hay sugerencias y trucos para asignar espacios.

## Administración del entorno

Hay dos valores de configuración que permiten a los usuarios "limpiar" hologramas y hacer que HoloLens "olvide" un espacio. Existen en **Hologramas y entornos** en la aplicación de configuración y la segunda opción de configuración también aparecen en **Privacidad** en la aplicación de configuración.  

1. **Eliminar hologramas cercanos**. Si seleccionas esta configuración, HoloLens borrará todos los hologramas anclados y todos los datos de mapa almacenados para el "espacio actual" en el que se encuentra el dispositivo. Se creará una nueva sección de mapa y se almacenará en la base de datos de esa ubicación una vez que los hologramas se vuelvan a colocar en el mismo espacio.

1. **Eliminar todos los hologramas**. Si seleccionas esta configuración, HoloLens borrará todos los datos de mapas y los hologramas anclados en todas las bases de datos de espacios. No se volverán a detectar hologramas y los hologramas tienen que haberse colocado recientemente para volver a almacenar secciones de mapas en la base de datos.

## Calidad de holograma

Los hologramas se pueden colocar en todo el entorno: alto, bajo y en cualquier lugar alrededor de ti, pero puedes verlos a través de un [marco holográfico](https://docs.microsoft.com/windows/mixed-reality/holographic-frame) que se encuentre delante de ti. Para obtener la mejor vista, asegúrate de ajustar el dispositivo para que puedas ver todo el marco. Y no dudes en recorrer tu entorno y explorarlo.

Para que tus [hologramas](https://docs.microsoft.com/windows/mixed-reality/hologram) tengan un aspecto nítido, claro y estable, tu HoloLens debe estar calibrado solo para ti. La primera vez que configures tu HoloLens, se te guiará por este proceso. Más adelante, si los hologramas no tienen el aspecto adecuado o ves muchos errores, podrás realizar ajustes.

Si tienes problemas para realizar mapas de espacios, intenta eliminar los hologramas cercanos y volver a crear un mapa del espacio.

### Calibración

Si los hologramas parecen inestables o se mueven, o si tienes problemas para colocar hologramas, lo primero que debes probar es la [aplicación Configuración](hololens-calibration.md). Esta aplicación también puede ayudarte si sientes molestias al usar tu HoloLens.

Para acceder a la aplicación Calibración, ve a **Configuración** > **Sistema** > **Utilidades**. Selecciona **Abrir calibración** y sigue las instrucciones.

Si otra persona va a usar tu HoloLens, debe ejecutar primero la aplicación Calibración para que el dispositivo se configure correctamente.

## Consulta también

- [Diseño de mapas espaciales](https://docs.microsoft.com/windows/mixed-reality/spatial-mapping)
- [Hologramas](https://docs.microsoft.com/windows/mixed-reality/hologram)
