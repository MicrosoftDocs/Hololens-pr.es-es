---
title: Solución de problemas
description: Manténgase al día de las soluciones más comunes para problemas de dispositivos HoloLens y técnicas de solución de problemas.
author: mattzmsft
ms.author: mazeller
ms.date: 12/02/2019
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: jarrettr
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: issues, bug, troubleshoot, fix, help, support, HoloLens
ms.openlocfilehash: 1039af533b5039eb4eef6599c7cbb480955b0661
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397266"
---
# <a name="troubleshoot-common-issues"></a>Solución de problemas comunes

En este artículo se describe cómo resolver varios problemas comunes de HoloLens.

## <a name="my-hololens-is-unresponsive-or-wont-start"></a>My HoloLens is unresponsive or won't start

Si holoLens no se inicia:

- Si los LED situados junto al botón de encendido no se encienden o solo un LED parpadea brevemente, es posible que deba cargar [holoLens.](hololens-recovery.md#charge-the-device)
- Si los LED se encienden al presionar el botón de encendido, pero no puede ver nada en las pantallas, debe realizar un restablecimiento de forma previa [del dispositivo.](hololens-recovery.md#hard-reset-procedure)

Si HoloLens se inmoviliza o deja de responder:

- Para desactivar HoloLens, presione el botón de encendido hasta que los cinco LED se apaguen a sí mismos o durante 15 segundos si los LED no responde. Para iniciar HoloLens, vuelva a presionar el botón de encendido.

Si estos pasos no funcionan, puede intentar recuperar el dispositivo [HoloLens 2](hololens-recovery.md) o [hololens (1.ª generación).](hololens1-recovery.md)

## <a name="holograms-dont-look-good"></a>Los hologramas no se ven bien

Si los hologramas son inestables, con saltos o no parecen correctos, pruebe lo siguiente:

- Limpiar el visor del dispositivo y la barra del sensor en la parte delantera de HoloLens.
- Aumentar la luz de la sala.
- Recorrer y examinar el entorno para que HoloLens pueda examinarlos más por completo.
- Calibrar HoloLens para los ojos. Vaya a **Configuración**  >  **Utilidades**  >  **del sistema**. En **Calibración,** seleccione **Abrir calibración.**
 
### <a name="reporting-issues-where-holograms-are-unstable-or-dont-look-right"></a>Informes de problemas en los que los hologramas son inestables o no son correctos
 
1. Grabe y un [Captura de realidad mixta vídeo](holographic-photos-and-videos.md#capture-a-mixed-reality-video) del problema. Este vídeo se puede cargar más adelante a través Centro de opiniones como un archivo adjunto.  
1. Habilite la telemetría  completa a través de la aplicación Configuración -> **Privacy**  ->  **Diagnostics & comentarios y,** en **Datos de diagnóstico opcionales,** asegúrese de que el botón de alternancia esté establecido en On **(Activar).**
1. Obtenga las correcciones más recientes de escala y estabilidad de hologramas mediante la actualización al sistema operativo [Windows Holographic más reciente(20H2 o superior).](hololens-release-notes.md#windows-holographic-version-20h2) Después de actualizar, realice lo siguiente:
    1. Quite todos los  hologramas a través de la aplicación Configuración -> **Hologramas** del sistema -> seleccione Quitar todos los hologramas y comience con  ->   un mapa nuevo. 
    1. Cree un nuevo mapa del espacio; para ello, pasee por holoLens y pasee por la sala y consulte todas las áreas y superficies del espacio. Haga esto entre 2 y 3 minutos.
    1. Realice la calibración de IPD. Vaya a **Configuración**  >  **Utilidades del**  >  **sistema**. En **Calibración,** seleccione **Abrir calibración.**
    1. Vuelva a probar el escenario y compruebe si todavía persiste.
1. Si la actualización no corrige el problema, envíe una Centro de opiniones [problema](hololens-feedback.md). Después de rellenar los comentarios,  puede usar el botón Compartir para crear un vínculo fácil de compartir que se puede enviar al ponerse en contacto con el soporte técnico.

## <a name="hololens-doesnt-respond-to-hand-input"></a>HoloLens no responde a la entrada de mano

Para asegurarse de que HoloLens puede ver las manos, debe mantenerlas en el marco de gestos.  El Mixed Reality Home proporciona comentarios que le permiten saber cuándo se realiza el seguimiento de las manos.  Los comentarios son diferentes en las distintas versiones de HoloLens:
- En HoloLens (1.ª generación), el cursor de mirada cambia de un punto a un anillo.
- En HoloLens 2, aparece un cursor de dedo cuando la mano está cerca de una pizarra y aparece un rayo cuando las pizarras están más lejos

Muchas aplicaciones envolventes siguen patrones de entrada similares a Mixed Reality Inicio.  Obtenga más información sobre el uso de la entrada a mano [en HoloLens (1ª generación)](hololens1-basic-usage.md#use-hololens-with-your-hands) [y HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).

Si va a llevar unas gafas, tenga en cuenta que algunos tipos de gafas no funcionan con el seguimiento de las manos.  Un ejemplo común es el de la caja negra, que tiende a absorber la luz de los rejas y no la toma la cámara de profundidad.  Si el trabajo implica una insondación de ruedas, se recomienda probar un color más claro, como azul o gris.  Otro ejemplo es una bolsa grande, que tiende a ocultar la forma de la mano. Se recomienda usar el mayor ajuste posible para obtener los mejores resultados.

Si el visor tiene huellas digitales o marcas, use la limpieza de microfibras que se incluye con HoloLens para limpiar el visor de forma natural.

## <a name="hololens-doesnt-respond-to-my-voice-commands"></a>HoloLens no responde a mis comandos de voz

Si Cortana no responde a los comandos de voz, asegúrese de que Cortana está activado. En la lista Todas las aplicaciones, seleccione **Configuración del** cuaderno de  >  **menús** de Cortana  >    >   para realizar cambios. Para más información sobre lo que puede decir, consulte [Uso de la voz con HoloLens.](hololens-cortana.md)

## <a name="i-cant-place-holograms-or-see-holograms-that-i-previously-placed"></a>No puedo colocar hologramas ni ver los hologramas que he colocado anteriormente

Si HoloLens no puede asignar ni cargar el espacio, entra en modo Limitado y no podrá colocar hologramas ni ver los hologramas que ha colocado. Estos son algunos aspectos que se pueden probar:

- Asegúrese de que hay suficiente luz en el entorno para que HoloLens pueda ver y asignar el espacio.
- Asegúrese de que está conectado a una red Wi-Fi virtual. Si no está conectado a wi-fi, HoloLens no puede identificar ni cargar un espacio conocido.
- Si necesita crear un espacio, conéctese a Wi-Fi y reinicie HoloLens.
- Para ver si el espacio correcto está activo o para cargar manualmente un espacio, vaya a **Configuración** de  >  **Espacios del**  >  **sistema**.
- Si se carga el espacio correcto y sigue teniendo problemas, es posible que el espacio esté dañado. Para corregir este problema, seleccione el espacio y, a continuación, **seleccione Quitar**. Después de quitar el espacio, HoloLens comienza a asignar el entorno y a crear un nuevo espacio.

## <a name="my-hololens-cant-tell-what-space-im-in"></a>My HoloLens can't tell what space I'm in (Mi HoloLens no puede saber en qué espacio estoy)

Si HoloLens no puede identificar y cargar automáticamente el espacio en el que se encuentra, compruebe los siguientes factores:

- Asegúrese de que está conectado a Wi-Fi
- Asegúrese de que hay mucha luz en la sala.
- Asegúrese de que no ha habido ningún cambio importante en el entorno.

También puede cargar un espacio manualmente o administrar los espacios si va a **Configuración**  >  **de Espacios del**  >  **sistema.**

## <a name="im-getting-a-low-disk-space-error"></a>Obtención de un error de "poco espacio en disco"

Deberá liberar espacio de almacenamiento haciendo uno o varios de los siguientes pasos:

- Elimine algunos espacios no usados. Vaya a **Configuración** Espacios del sistema, seleccione un espacio que ya no necesite  >    >  y, a continuación, **seleccione Quitar**.
- Quite algunos de los hologramas que ha colocado.
- Elimine algunas imágenes y vídeos de la aplicación Fotos.
- Desinstale algunas aplicaciones de HoloLens. En la **lista Todas las** aplicaciones, mantenga presionada la aplicación que desea desinstalar y, a continuación, seleccione **Desinstalar**.

## <a name="my-hololens-cant-create-a-new-space"></a>My HoloLens no puede crear un nuevo espacio

El problema más probable es que se está quedando sin espacio de almacenamiento. Pruebe una de las [sugerencias anteriores](#im-getting-a-low-disk-space-error) para liberar espacio en disco.

## <a name="the-hololens-emulator-isnt-working"></a>El emulador de HoloLens no funciona

La información sobre el emulador de HoloLens se encuentra en nuestra documentación para desarrolladores.  Obtenga más información sobre [cómo solucionar problemas del emulador de HoloLens.](https://docs.microsoft.com/windows/mixed-reality/using-the-hololens-emulator#troubleshooting)
