---
title: Solución de problemas
description: Soluciones para problemas comunes de HoloLens.
author: mattzmsft
ms.author: mazeller
ms.date: 12/02/2019
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
keywords: problemas, error, solución de problemas, corrección, ayuda, soporte técnico, HoloLens
manager: jarrettr
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.openlocfilehash: 469848cf306675fcfb99247b5c91b159c204a5fe
ms.sourcegitcommit: 2122490074adb7f63edfc3576441980caa22695f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2020
ms.locfileid: "10915963"
---
# Solución de problemas

En este artículo se describe cómo resolver varios problemas comunes de HoloLens.

## Mi HoloLens no responde o no se inicia

Si HoloLens no se inicia:

- Si los LEDs junto al botón de encendido no se encienden o si solo parpadean unos LED, es posible que debas [cobrarte por tu HoloLens.](hololens-recovery.md#charge-the-device)
- Si los LEDs se encienden al presionar el botón de encendido pero no puede ver nada en las pantallas, [preform un reinicio rígido del dispositivo](hololens-recovery.md#hard-reset-procedure).

Si HoloLens se inmoviliza o no responde:

- Para desactivar HoloLens, pulsa el botón de encendido hasta que los cinco LEDs se desactiven o durante 15 segundos si los LEDs no responden. Para iniciar HoloLens, vuelve a pulsar el botón de encendido.

Si estos pasos no funcionan, puede intentar [recuperar el dispositivo hololens 2](hololens-recovery.md) o [hololens (1. ª gen).](hololens1-recovery.md)

## Los hologramas no parecen buenos

Si los hologramas son inestables, saltan o no tienen el aspecto correcto, pruebe lo siguiente:

- Limpia el visor del dispositivo y la barra de la parte frontal de tu HoloLens.
- Aumento de la luz de su habitación.
- Caminar y mirando tu entorno para que HoloLens pueda explorarlos de forma más completa.
- Calibra tu HoloLens para tus ojos. Vaya a **configuración**  >  **utilidades del sistema**  >  **Utilities**. En **Calibración**, seleccione **Abrir calibración**.

## HoloLens no responde a la entrada de la mano

Para asegurarte de que HoloLens pueda ver tus manos, debes mantenerlos en el marco de gestos.  La Página principal de la realidad mixta proporciona comentarios que te permiten saber cuándo se realiza el seguimiento de las manos.  Los comentarios son diferentes en diferentes versiones de HoloLens:
- En HoloLens (1ª generación), el cursor de fijamente cambia de un punto a un anillo
- En HoloLens 2, el cursor de la mano aparece cuando la mano está cerca de un Slate, y se muestra un rayo de mano cuando se alejan las tabletas.

Muchas aplicaciones envolventes siguen patrones de entrada que son similares a la Página principal de la realidad mixta.  Obtén más información sobre cómo usar la entrada de la mano en [HoloLens (1. ª gen)](hololens1-basic-usage.md#use-hololens-with-your-hands) y [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).

Si está usando guantes, tenga en cuenta que algunos tipos de guantes no funcionan con el seguimiento manual.  Un ejemplo común son guantes de goma negro, que tienden a absorber la luz infrarroja y que la cámara de profundidad no recoge.  Si su trabajo incluye guantes de goma, le recomendamos que pruebe un color más claro, como azul o gris.  Otro ejemplo es una gran cantidad de guantes de baggy, que tiende a oscurecer la forma de la mano. Para obtener los mejores resultados, le recomendamos que use guantes que se ajusten como sea posible.

Si tu visor tiene huellas o manchas, usa el paño de limpieza microfiber que venía con HoloLens para limpiar el visor suavemente.

## HoloLens no responde a mis comandos de voz

Si Cortana no responde a tus comandos de voz, asegúrate de que Cortana esté activada. En la lista todas las aplicaciones, seleccione Configuración del Bloc de notas del menú **Cortana**  >  **Menu**  >  **Notebook**  >  **Settings** para realizar cambios. Para saber más sobre lo que puede decir, consulte [Use su voz con el HoloLens](hololens-cortana.md).

## No puedo colocar hologramas o ver hologramas que he colocado anteriormente

Si HoloLens no puede asignar ni cargar tu espacio, entra en el modo limitado y no podrás colocar hologramas ni ver hologramas que haya colocado. Puedes intentar lo siguiente:

- Asegúrate de que haya suficiente luz en tu entorno para que HoloLens pueda ver y asignar el espacio.
- Asegúrate de estar conectado a una red Wi-Fi. Si no estás conectado a una red Wi-Fi, HoloLens no puede identificar ni cargar un espacio conocido.
- Si necesita crear un nuevo espacio, conéctese a una red Wi-Fi y, a continuación, reinicie HoloLens.
- Para ver si el espacio correcto está activo o para cargar manualmente un espacio, vaya a **configuración**  >  **espacios del sistema**  >  **Spaces**.
- Si se carga el espacio correcto y sigues teniendo problemas, el espacio puede estar dañado. Para solucionar este problema, seleccione el espacio y, después, haga clic en **quitar**. Después de quitar el espacio, HoloLens comienza a asignar el entorno y a crear un nuevo espacio.

## Mi HoloLens no puede saber qué espacio estoy en

Si HoloLens no puede identificar ni cargar el espacio en el que se encuentra automáticamente, compruebe los siguientes factores:

- Asegúrate de estar conectado a una red Wi-Fi
- Asegúrese de que hay mucha luz en el salón
- Asegúrese de que no haya ningún cambio importante en el entorno.

También puedes cargar un espacio manualmente o administrar tus espacios yendo a **configuración**  >  **espacios del sistema**  >  **Spaces**.

## Obtengo un error de "poco espacio en el disco"

Tendrás que liberar algo de espacio de almacenamiento mediante uno o varios de los siguientes procedimientos:

- Elimine algunos espacios que no se hayan usado. Vaya a **configuración**  >  **espacios del sistema**  >  **Spaces**, seleccione un espacio que ya no necesite y, después, seleccione **quitar**.
- Quite algunos hologramas que haya colocado.
- Elimine algunas imágenes y vídeos de la aplicación fotos.
- Desinstale algunas aplicaciones de su HoloLens. En la lista **todas las aplicaciones** , pulse y mantenga presionada la aplicación que quiera desinstalar y, después, seleccione **desinstalar**.

## Mi HoloLens no puede crear un nuevo espacio

Lo más probable es que se esté agotando el espacio de almacenamiento. Pruebe una de las [sugerencias anteriores](#im-getting-a-low-disk-space-error) para liberar espacio en disco.

## El emulador de HoloLens no funciona

La información sobre el emulador de HoloLens se encuentra en nuestra documentación para desarrolladores.  Más información sobre cómo [solucionar problemas del emulador de HoloLens](https://docs.microsoft.com/windows/mixed-reality/using-the-hololens-emulator#troubleshooting).
