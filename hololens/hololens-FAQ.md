---
title: Preguntas más frecuentes sobre HoloLens dispositivos y hologramas
description: ¿Tiene alguna pregunta rápida sobre la HoloLens o la interacción con hologramas?  En este artículo se proporciona una respuesta rápida y más recursos.
keywords: hololens, preguntas más frecuentes, problema conocido, ayuda
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
ms.date: 02/27/2020
ms.reviewer: ''
ms.custom:
- CI 114606
- CSSTroubleshooting
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: b20e5784711fdbae0602943cbad35a37f5be72fdd2a709ec8c04d95b05e75ada
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664628"
---
# <a name="holograms-and-interactions-troubleshooting"></a>Hologramas solución de problemas de Hologramas e interacciones

En este artículo se solucionan problemas relacionados con la colocación de hologramas, el trabajo con espacios y la informes de problemas con hologramas.

Siempre que tenga problemas, asegúrese de:
- Intente [reiniciarlo para](hololens-restart-recover.md) ver si eso corrige las cosas.
- Antes de solucionar problemas, asegúrese de HoloLens [se cobra](hololens2-charging.md) (se cobra durante al menos una hora). 


Use la aplicación Comentarios para enviarnos información sobre el problema. Encontrará la aplicación Comentarios en el [ **menú** Inicio](holographic-home.md). 

Para obtener sugerencias sobre cómo usar el HoloLens, consulte [Ajustar ajuste.](hololens2-setup.md#adjust-fit)

<a id="list"></a>
- [No se pueden crear nuevos espacios](#new-spaces-cant-be-created)
- [Los espacios no se pueden identificar ni cargar](#spaces-cant-be-identified-or-loaded)
- [Cómo eliminar todos los espacios?](#how-do-i-delete-all-spaces)
- [Hologramas no se ven bien o se mueven](#holograms-dont-look-right-or-are-moving-around)
- [Mensaje "Búsqueda del espacio"](#finding-your-space-message)
- [Los hologramas esperados no se muestran en mi espacio](#expected-holograms-arent-showing-in-my-space)
- [No se pueden colocar hologramas ni ver hologramas colocados anteriormente](#cant-place-holograms-or-see-previously-placed-holograms)
- [Hologramas desaparecen o están incluidos en otros hologramas u objetos](#holograms-disappear-or-are-encased-in-other-holograms-or-objects)
- [Hologramas aparecen en el otro lado de una pared](#holograms-are-appearing-on-the-other-side-of-a-wall)
- [Después de colocar un holograma en una pared, parece flotar](#after-placing-a-hologram-on-a-wall-it-seems-to-float)
- [Las aplicaciones aparecen demasiado cerca después de moverlas](#apps-appear-too-close-after-moving-them)
- [Informes de problemas con hologramas inestables o inexactos](#reporting-issues-with-unstable-or-inexact-holograms)

## <a name="new-spaces-cant-be-created"></a>No se pueden crear nuevos espacios

El problema más probable es que se está quedando sin espacio de almacenamiento. [Liberar espacio en disco y, a](hololens-troubleshooting.md#low-disk-space-error) continuación, volver a intentarlo.

[Volver a la lista](#list)

## <a name="spaces-cant-be-identified-or-loaded"></a>Los espacios no se pueden identificar ni cargar

Si el HoloLens no puede identificar y cargar automáticamente el espacio en el que se encuentra, compruebe los siguientes factores:

- Asegúrese de que está conectado a Wi-Fi
- Asegúrese de que hay mucha luz en la sala.
- Asegúrese de que no ha habido ningún cambio importante en el entorno.

También puede cargar un espacio manualmente o administrar los espacios si va a Configuración  >  **Espacios del**  >  **sistema**.

[Volver a la lista](#list)

## <a name="how-do-i-delete-all-spaces"></a>Cómo eliminar todos los espacios?

*Próximamente*

[Volver a la lista](#list)

## <a name="holograms-dont-look-right-or-are-moving-around"></a>Hologramas no se ven bien o se mueven

Si los hologramas no tienen el aspecto correcto (por ejemplo, son de vibración o de vibración, o ves revisiones negras encima de ellos), prueba una de estas correcciones:

- [Limpie el visor del dispositivo](hololens1-hardware.md#care-and-cleaning) y asegúrese de que no hay nada que bloquee los sensores.
- Asegúrese de que se encuentra en una sala bien iluminación que no tiene mucha luz directa.
- Pruebe a recorrer y mirar el entorno para que HoloLens pueda examinarlos más por completo.
- Si ha colocado muchos hologramas, intente quitar algunos.

Si sigue teniendo problemas, intente ejecutar la aplicación calibración. Esta aplicación calibra su HoloLens solo para que le ayude a mantener los hologramas con su mejor aspecto. Para ello, vaya a **Configuración**  >  **Utilidades del**  >  **sistema**. En **Calibración,** seleccione **Abrir calibración.**

[Volver a la lista](#list)

## <a name="finding-your-space-message"></a>Mensaje "Búsqueda del espacio"

Cuando HoloLens está aprendiendo o cargando un espacio, es posible que vea un breve mensaje que dice "Búsqueda del espacio". Si este mensaje se muestra durante más de unos segundos, verá otro mensaje en el menú Inicio que dice "Todavía buscando el espacio".

Estos mensajes significan que HoloLens tiene problemas para asignar el espacio. Cuando esto sucede, puede abrir aplicaciones, pero no puede colocar hologramas en su entorno.

Si ve estos mensajes con frecuencia, pruebe una o varias de las correcciones siguientes:

- Asegúrese de que se encuentra en una sala bien iluminación que no tiene mucha luz directa.
- Asegúrese de que el visor del dispositivo está limpio. [Obtenga información sobre cómo limpiar el visor](hololens1-hardware.md#care-and-cleaning).
- Asegúrese de que tiene una señal de Wi-Fi segura. Si escribe un nuevo entorno que no tiene ninguna Wi-Fi o una señal de Wi-Fi débil, HoloLens no podrá encontrar el espacio. Para comprobar Wi-Fi conexión, vaya **a Configuración** Red  >  **&amp;**  >  **Wi-Fi de Internet.**
- Intente moverse más lentamente.

[Volver a la lista](#list)

## <a name="expected-holograms-arent-showing-in-my-space"></a>Los hologramas esperados no se muestran en mi espacio

Si no ve los hologramas que ha colocado o si ve algunos que no espera, pruebe una o varias de las correcciones siguientes:

- Encienda algunas luces. HoloLens funciona mejor en un espacio bien encendido.
- Quite los hologramas que no necesite; para ello, vaya a Configuración   >  **System**  >  **Hologramas**  >  Remove nearby holograms (Quitar **hologramas cercanos).** O bien, si es necesario, seleccione **Quitar todos los hologramas.**

  > [!NOTE]
  > Si el diseño o la iluminación del espacio cambian significativamente, es posible que el dispositivo tenga problemas para identificar el espacio y mostrar los hologramas.

[Volver a la lista](#list)

## <a name="cant-place-holograms-or-see-previously-placed-holograms"></a>No se pueden colocar hologramas ni ver hologramas colocados anteriormente

Si HoloLens asignar o cargar el espacio, entra en modo Limitado y no podrá colocar hologramas ni ver los hologramas que ha colocado. Estos son algunos aspectos que se pueden probar:

- Asegúrese de que hay suficiente luz en el entorno para HoloLens ver y asignar el espacio.
- Se encuentra entre uno y tres metros desde donde está intentando colocar el holograma.
- No coloque hologramas en superficies negra o reflectante.
- Asegúrese de que está conectado a una red Wi-Fi virtual. Si no está conectado a Wi-Fi, HoloLens identificar y cargar un espacio conocido.
- Pasee por las salas para HoloLens pueda volver a examinar su entorno. Para ver lo que ya se ha examinado, pulse en el aire para mostrar el gráfico de malla de asignación.
- Si necesita crear un espacio, conéctese a Wi-Fi y reinicie el HoloLens.
- Para ver si el espacio correcto está activo o para cargar manualmente un espacio, vaya a Configuración  >  **Espacios del**  >  **sistema**.
- Si se carga el espacio correcto y sigue teniendo problemas, es posible que el espacio esté dañado. Para corregir este problema, seleccione el espacio y, a continuación, **seleccione Quitar**. Después de quitar el espacio, HoloLens empieza a asignar el entorno y a crear un nuevo espacio.

[Volver a la lista](#list)

## <a name="holograms-disappear-or-are-encased-in-other-holograms-or-objects"></a>Hologramas desaparecen o están incluidos en otros hologramas u objetos

Si te acercas demasiado a un holograma, desaparecerá temporalmente para restaurar el holograma, simplemente &mdash; aléjate de él. Además, si ha colocado varios hologramas juntos, algunos pueden desaparecer. Intente quitar algunas.

Hologramas también se pueden bloquear o encaste otros hologramas o objetos como las paredes. Si esto sucede, pruebe una de las siguientes correcciones:

- Si el holograma está encerrado en otro holograma, mueva el holograma encasado a otra ubicación. Para ello, seleccione **Ajustar** y, a continuación, pulse y mantenga presionado para colocarlo.
- Si el holograma está encerrado en una pared, seleccione **Ajustar** y, a continuación, avance hacia la pared hasta que aparezca el holograma. Pulse y mantenga presionado y, a continuación, extraiga el holograma hacia delante y fuera de la pared.
- Si no puede mover el holograma mediante gestos, use la voz para quitarlo. Mire el holograma y, a continuación, diga "Quitar". A continuación, vuelva a abrir el holograma y colóctelo en una nueva ubicación.

[Volver a la lista](#list)

## <a name="holograms-are-appearing-on-the-other-side-of-a-wall"></a>Hologramas aparecen en el otro lado de una pared

Si está muy cerca de una pared o HoloLens todavía no ha examinado la pared, puede ver los hologramas que se encuentran en la siguiente sala. Para examinar la pared, de pie entre uno y tres metros de la pared y mire hacia ella.

Un objeto negro o reflectante (por ejemplo, un cómodo negro o un refrigerador de cristal) cerca de la pared puede causar problemas HoloLens intentar examinar la pared. Si hay un objeto de este tipo, escalo el otro lado de la pared.

[Volver a la lista](#list)

## <a name="after-placing-a-hologram-on-a-wall-it-seems-to-float"></a>Después de colocar un holograma en una pared, parece flotar

Normalmente, un holograma que se coloca en una pared parece estar a una pulgada o así de la pared. Si parece que está más lejos, pruebe una o varias de las correcciones siguientes:

- Cuando coloque un holograma en una pared, desántese entre uno y tres metros de la pared y desándalo directamente.
- Pulse el aire en la pared para mostrar el gráfico de malla de asignación. Asegúrese de que la malla se alinea con la pared. Si no es así, quite el holograma, vuelva a examinar la pared e inténtelo de nuevo.
- Si el problema persiste, ejecute la aplicación Calibración. Lo encontrará en Configuración  >  **utilidades**  >  **del sistema**.

[Volver a la lista](#list)

## <a name="apps-appear-too-close-after-moving-them"></a>Las aplicaciones aparecen demasiado cerca después de moverlas

Pruebe a recorrer y ver el área donde va a colocar la aplicación para HoloLens el área desde distintos ángulos. [Limpiar el visor del dispositivo](hololens1-hardware.md#care-and-cleaning) también puede ayudar.

[Volver a la lista](#list)

## <a name="reporting-issues-with-unstable-or-inexact-holograms"></a>Informes de problemas con hologramas inestables o inexactos
 
1. Grabe y un [Captura de realidad mixta vídeo](holographic-photos-and-videos.md#capture-a-mixed-reality-video) del problema. Este vídeo se puede cargar más adelante a través de Centro de opiniones como un archivo adjunto.  
1. Habilite la telemetría completa a través de **Configuración** app -> **Privacy** Diagnostics & comentarios y, en Datos de diagnóstico opcionales, asegúrese de que el botón de alternancia  ->   esté establecido en On **(Activar).** 
1. Obtenga las correcciones más recientes de escala y estabilidad de hologramas mediante la actualización a la versión más reciente Windows sistema operativo [Holográfico, (20H2 o superior).](hololens-release-notes.md#windows-holographic-version-20h2) Después de actualizar, realice lo siguiente:
    1. Quite todos los Hologramas a través de **Configuración** app -> **System**  ->  **Hologramas** ->, seleccione Quitar todos los hologramas y comience con un mapa nuevo. 
    1. Cree un nuevo mapa del espacio, para lo que debe HoloLens y recorrer la sala y ver todas las áreas y superficies del espacio. Haga esto durante 2-3 minutos.
    1. Realice la calibración de IPD. Vaya **a** Configuración  >  **Utilidades del**  >  **sistema**. En **Calibración,** seleccione **Abrir calibración.**
    1. Vuelva a probar el escenario y compruebe si todavía persiste.
1. Si la actualización no corrige el problema, envíe un Centro de opiniones [problema](hololens-feedback.md). Después de rellenar los comentarios,  puede usar el botón Compartir para crear un vínculo fácil de compartir que se puede enviar al ponerse en contacto con el soporte técnico.

[Volver a la lista](#list)