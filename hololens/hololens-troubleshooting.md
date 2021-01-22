---
title: Solución de problemas
description: Manténgase al día sobre las soluciones más comunes para problemas de dispositivos HoloLens y técnicas de solución de problemas.
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
keywords: problemas, error, solucionar problemas, corregir, ayuda, soporte técnico, HoloLens
ms.openlocfilehash: f57aea52337f7ca7e15bda1363f73a3a7265a025
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283051"
---
# Solución de problemas

En este artículo se describe cómo resolver varios problemas comunes de HoloLens.

## My HoloLens is unresponsive or won't start

Si holoLens no se inicia:

- Si los LED situados junto al botón de encendido no se encienden o solo un LED parpadea brevemente, es posible que deba cargar [su HoloLens.](hololens-recovery.md#charge-the-device)
- Si los LEDs se encienden al presionar el botón de encendido, pero no se puede ver nada en las pantallas, [preformar](hololens-recovery.md#hard-reset-procedure)un restablecimiento completo del dispositivo.

Si holoLens se inmoviliza o deja de responder:

- Apaga HoloLens presionando el botón de encendido hasta que los cinco LEDs se apaguen a sí mismos o durante 15 segundos si los LEDs no responden. Para iniciar HoloLens, vuelva a presionar el botón de encendido.

Si estos pasos no funcionan, puedes intentar recuperar el dispositivo [HoloLens 2](hololens-recovery.md) o el dispositivo [HoloLens (1.ª generación).](hololens1-recovery.md)

## Los hologramas no se ven bien

Si los hologramas son inestables, saltando o no se ven bien, pruebe:

- Limpiar el visor del dispositivo y la barra del sensor en la parte frontal de HoloLens.
- Aumentar la luz de la sala.
- Paseando y mirando a su entorno para que HoloLens pueda examinarlos más completamente.
- Calibrar HoloLens para tus ojos. Vaya a **Utilidades**  >  **del sistema de**  >  **configuración.** En **Calibración**, seleccione **Abrir calibración**.
 
### Notificar problemas en los que los hologramas son inestables o no son correctos
 
1. Grabe y un [vídeo de captura](holographic-photos-and-videos.md#capture-a-mixed-reality-video) de realidad mixta del problema. Este vídeo se puede cargar más adelante a través del Centro de opiniones como un archivo adjunto.  
1. Habilitar telemetría completa **** a través de la aplicación Configuración -> **Comentarios**de diagnóstico de privacidad & y, en Datos de diagnóstico opcionales, garantizar que el botón de alternancia  ->  **** esté establecido en **Activar** ****
1. Obtenga las correcciones más recientes de escala y estabilidad de hologramas mediante la actualización a la versión más reciente del sistema operativo [Windows Holographic (20H2 o superior).](hololens-release-notes.md#windows-holographic-version-20h2) Después de actualizar, realice lo siguiente:
    1. Quita todos los **** hologramas a través de la aplicación Configuración -> **Hologramas**del sistema -> luego selecciona Quitar todos los hologramas y empieza  ->  **** con un mapa nuevo. ****
    1. Crea un nuevo mapa de tu espacio usando holoLens y paseando por la sala y mirando todas las áreas y superficies del espacio. Haga esto durante 2-3 minutos.
    1. Realiza la calibración de IPD. Vaya a **Utilidades**  >  **del sistema de**  >  **configuración.** En **Calibración**, seleccione **Abrir calibración**.
    1. Vuelva a probar el escenario y vea si aún persiste.
1. Si la actualización no soluciona el problema, envíe un problema [del Centro de opiniones.](hololens-feedback.md) Después de rellenar los comentarios, **** puede usar el botón Compartir para crear un vínculo fácil de compartir que se puede enviar al ponerse en contacto con el soporte técnico.

## HoloLens no responde a la entrada de mano

Para asegurarte de que HoloLens pueda ver tus manos, debes mantenerlas en el marco de gestos.  La página principal de realidad mixta proporciona comentarios que te permiten saber cuándo se realiza un seguimiento de las manos.  Los comentarios son diferentes en diferentes versiones de HoloLens:
- En HoloLens (1.ª generación), el cursor de mirada cambia de un punto a un anillo
- En HoloLens 2, aparece un cursor de dedo cuando la mano está cerca de una pizarra y aparece un rayo de mano cuando las pizarras están más lejos

Muchas aplicaciones envolventes siguen patrones de entrada similares a Mixed Reality Home.  Obtenga más información sobre cómo usar la entrada de mano [en HoloLens (1.ª generación)](hololens1-basic-usage.md#use-hololens-with-your-hands) y [HoloLens 2.](hololens2-basic-usage.md#the-hand-tracking-frame)

Si vas a llevar el uniforme, ten en cuenta que algunos tipos de clase no funcionan con el seguimiento de manos.  Un ejemplo común es la insondencia negra, que tiende a absorber la luz infrarroja y no la toma la cámara de profundidad.  Si tu trabajo implica una insondación, te recomendamos probar un color más claro, como azul o gris.  Otro ejemplo es una bolsa grande, que tiende a oscurecer la forma de la mano. Se recomienda usar unas prácticas que sean lo más apropiadas posible para obtener los mejores resultados.

Si el visor tiene huellas digitales o manchas, usa el trapeador de limpieza de microfibras que viene con HoloLens para limpiar el visor con su mente.

## HoloLens no responde a mis comandos de voz

Si Cortana no responde a los comandos de voz, asegúrate de que Cortana esté activada. En la lista Todas las aplicaciones, selecciona Configuración del bloc de notas de menú de **Cortana**  >  ****  >  ****  >  **** para realizar cambios. Para saber más sobre lo que puede decir, consulte [Use su voz con el HoloLens](hololens-cortana.md).

## No puedo colocar hologramas ni ver hologramas que he colocado anteriormente

Si HoloLens no puede asignar o cargar el espacio, entra en modo Limitado y no podrás colocar hologramas ni ver hologramas que hayas colocado. Puedes intentar lo siguiente:

- Asegúrate de que tu entorno tiene suficiente luz para que HoloLens pueda ver y asignar el espacio.
- Asegúrese de que está conectado a una Wi-Fi web. Si no estás conectado a la red Wi-Fi, HoloLens no puede identificar ni cargar un espacio conocido.
- Si necesitas crear un espacio nuevo, conéctate a La Wi-Fi y reinicia HoloLens.
- Para ver si el espacio correcto está activo o para cargar manualmente un espacio, vaya a **Configuración**de espacios  >  **del**  >  **sistema.**
- Si se carga el espacio correcto y sigue teniendo problemas, es posible que el espacio esté dañado. Para solucionar este problema, seleccione el espacio y, a continuación, **seleccione Quitar**. Después de quitar el espacio, HoloLens comienza a asignar su entorno y a crear un nuevo espacio.

## My HoloLens can't tell what space I'm in

Si holoLens no puede identificar y cargar automáticamente el espacio en el que se encuentra, compruebe los siguientes factores:

- Asegúrese de que está conectado a Wi-Fi
- Asegúrese de que hay mucha luz en la sala
- Asegúrate de que no se hayan realizado cambios importantes en el entorno.

También puede cargar un espacio manualmente o administrar los espacios yendo a **Configuración**  >  **de espacios del**  >  **sistema.**

## Aparece un error de "poco espacio en disco"

Deberá liberar espacio de almacenamiento realizando una o varias de las siguientes acciones:

- Elimine algunos espacios sin usar. Vaya a **Espacios**  >  **del sistema**de configuración, seleccione un espacio que ya no necesite  >  **** y, a continuación, **seleccione Quitar**.
- Quita algunos de los hologramas que has colocado.
- Elimina algunas imágenes y vídeos de la Fotos aplicación.
- Desinstale algunas aplicaciones de su HoloLens. En la **lista Todas las** aplicaciones, pulse y mantenga presionada la aplicación que desea desinstalar y, a continuación, seleccione **Desinstalar**.

## Mi HoloLens no puede crear un espacio nuevo

El problema más probable es que se está quedando sin espacio de almacenamiento. Pruebe una de las [sugerencias anteriores](#im-getting-a-low-disk-space-error) para liberar espacio en disco.

## El emulador de HoloLens no funciona

La información sobre el emulador de HoloLens se encuentra en nuestra documentación para desarrolladores.  Obtenga más información [sobre cómo solucionar problemas del emulador de HoloLens.](https://docs.microsoft.com/windows/mixed-reality/using-the-hololens-emulator#troubleshooting)
