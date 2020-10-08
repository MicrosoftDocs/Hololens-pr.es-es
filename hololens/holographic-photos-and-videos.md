---
title: Capturar y administrar fotos y videos de realidad mixta
description: Obtén información sobre cómo capturar, ver y compartir fotos y videos de realidad mixta con HoloLens.
keywords: hololens, Foto, vídeo, captura, MRC, captura de realidad mixta, fotos, cámara, flujo, Livestream, demostración
ms.assetid: 1b636ec3-6186-4fbb-81b2-71155aef0593
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
ms.date: 10/28/2019
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 4da70e73cd5949c77bc77a73f57f788ed51eff90
ms.sourcegitcommit: 973b0e71ebceeb2c614aea3dd3a1fbb90d7daed9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2020
ms.locfileid: "11100275"
---
# Crear fotos y vídeos de realidad mixta

HoloLens ofrece a los usuarios la experiencia de mezclar el mundo real con el mundo digital.  La captura de realidad mixta (MRC) te permite capturar esa experiencia como una foto o un vídeo, o compartir lo que ves con otras personas en tiempo real.

La captura de realidad mixta usa un punto de vista de primera persona para que otras personas puedan ver los hologramas a medida que los ven. Para un punto de vista de terceras personas, use la [vista Spectator](https://docs.microsoft.com/windows/mixed-reality/spectator-view). La vista Spectator es especialmente útil para demostraciones.

Aunque es divertido compartir vídeos entre amigos y colegas, los vídeos también pueden ayudar a enseñar a otras personas a usar una aplicación o a comunicar problemas con aplicaciones y experiencias.

> [!NOTE]
> Si no puede iniciar experiencias de captura de realidad mixta y su HoloLens es un dispositivo de trabajo, consulte al administrador del sistema. El acceso a la cámara se puede restringir mediante la política de la empresa.

## Capturar una foto de realidad mixta

Hay varias maneras de tomar una fotografía de la realidad mixta en HoloLens; puede usar botones de hardware, voz o el menú Inicio.

### Botones de hardware para tomar fotografías

Para tomar una foto rápida de la vista actual, pulsa los botones subir volumen y bajar el volumen al mismo tiempo.  Esto es algo como la versión HoloLens de una captura de pantalla o una pantalla de impresión.

- [Ubicaciones de los botones en HoloLens 2](hololens2-hardware.md)
- [Ubicaciones de los botones en HoloLens (1ª generación)](hololens1-hardware.md#hololens-components)

> [!NOTE]
> Los botones **subir** de volumen y **bajar el volumen** de tres segundos comenzarán a grabar un video en lugar de tomar una foto. Para detener la grabación, pulse los botones **subir volumen** y **bajar volumen** simultáneamente.

### Comandos de voz para tomar fotografías

En HoloLens 2, versión 2004 (y posteriores), diga: "tomar una foto".

En HoloLens (1. ª gen) o HoloLens 2, versión 1903, diga: "Hola Cortana, tomar una foto".

### Menú Inicio para tomar fotografías

Use el gesto de inicio para ir a **Inicio**y, a continuación, seleccione el icono de **cámara** .

Apunta a tu cabeza en la dirección de lo que deseas capturar y luego [toca el avión](hololens2-basic-usage.md#touch-holograms-near-you) para tomar una foto. Puedes seguir usando el avión y captar fotos adicionales. Todas las fotos que capture se guardarán en el dispositivo.

Vuelva a usar el gesto de inicio para finalizar la captura de fotos.  

## Capturar un vídeo de realidad mixta

Hay varias maneras de grabar un vídeo de realidad mixta en HoloLens; puede usar botones de hardware, voz o el menú Inicio.

### Botones de hardware para grabar vídeos

La manera más rápida de grabar un vídeo es mantener presionados los botones **subir volumen** y **bajar el volumen** hasta que se inicie un recuento de tres segundos. Para detener la grabación, puntee dos botones a la vez.

> [!NOTE]
> Al pulsar rápidamente los botones **subir volumen** y **bajar el volumen** , se tomará una foto en lugar de grabar un video.

### Voz para grabar vídeos

En HoloLens 2, versión 2004 (y posteriores), diga: "iniciar grabación". Para detener la grabación, diga "Detener grabación".

En HoloLens (1. ª gen) o HoloLens 2, versión 1903, diga: "Hola Cortana, iniciar grabación". Para detener la grabación, di "Hola Cortana, detener la grabación".

### Menú Inicio para grabar vídeos

Use el gesto de inicio para ir a **Inicio**y, a continuación, seleccione el icono **vídeo** . Apunta a tu cabeza en la dirección de lo que deseas capturar y luego [toca el avión](hololens2-basic-usage.md#touch-holograms-near-you) para empezar a grabar. Habrá una cuenta atrás de tres segundos y la grabación comenzará.

Para detener la grabación, use el gesto de inicio y seleccione el icono de **vídeo** resaltado. El vídeo se guardará en el dispositivo.

> [!NOTE]
> **Solo se aplica a HoloLens (1. ª gen)**  
> La [actualización de Windows 10 de octubre de 2018](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018) cambia cómo se comportan el botón iniciar y el botón Windows en HoloLens (1. ª generación). Antes de la actualización, el botón iniciar o cerrar Windows detendría una grabación de video. Después de la actualización, sin embargo, el botón iniciar o quitar ventanas abre el menú **Inicio** (o el **menú de acciones rápidas** si está en una aplicación envolvente), en el que puede seleccionar el icono de **vídeo** resaltado para detener la grabación.

## Comparte lo que ves en tiempo real

Puedes compartir lo que ves en HoloLens con amigos y colegas en tiempo real. Hay algunos métodos disponibles:

1. Conexión a un dispositivo o adaptador de Miracast para verlo en un televisor.
1. Uso de [Windows Device portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) para vigilar en un equipo PC
1. Usar la [aplicación complementaria de Microsoft HoloLens](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) para ver en un equipo PC.
1. Implementar la aplicación de [asistencia remota de Microsoft Dynamics 365](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist) , que permite a los trabajadores de las líneas frontals transmitir lo que ven a un experto remoto. El experto remoto puede entonces guiar verbalmente con el trabajador de primera línea o realizando anotaciones en su mundo.

> [!NOTE]
> Compartir lo que ves a través de Windows Device portal o de la aplicación complementaria de Microsoft HoloLens requiere que HoloLens esté en [modo de desarrollador](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal).

### Vídeo de transmisión con Miracast

Use el gesto de inicio para ir a **Inicio**y, a continuación, seleccione el icono **conectar** . En el selector que aparece, seleccione el dispositivo o adaptador con Miracast habilitado al que desea conectarse.

Para dejar de compartir, use el gesto de inicio y seleccione el icono de **conexión** resaltado. Como estabas transmitiendo, no se guardará nada en tu dispositivo.

> [!NOTE]
> La compatibilidad de Miracast se habilitó en HoloLens (1 ª generación) a partir de la [actualización de Windows 10 de octubre de 2018](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018).

### Vídeo en tiempo real con Windows Device portal

Como compartir a través de Windows Device Portal requiere que el modo de desarrollador esté habilitado en HoloLens, sigue las instrucciones de nuestra documentación para desarrolladores para [configurar el modo de desarrollador y navegar por Windows Device portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).

### Aplicación complementaria de Microsoft HoloLens

Como compartir a través de la aplicación de complemento de HoloLens requiere que el modo de desarrollador esté habilitado en HoloLens, sigue las instrucciones de nuestra documentación para desarrolladores para [configurar el modo de desarrollador](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal). Después, descarga la [aplicación complementaria de Microsoft hololens](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) y sigue las instrucciones de la aplicación para conectarte a HoloLens.

Una vez que la aplicación esté configurada con HoloLens, seleccione la opción de **flujo en vivo** en el menú principal de la aplicación.

## Ver las fotos y los vídeos de realidad mixta

Las fotos y los vídeos de realidad mixta se guardan en el "álbum de cámara" del dispositivo. Puedes examinar el contenido de esta carpeta en HoloLens con la aplicación explorador de archivos (ir a imágenes > álbum de cámara).

También puede ver sus fotos y vídeos de realidad mixta en la aplicación fotos, que está preinstalada en HoloLens. Para anclar una foto de su mundo, selecciónela en la aplicación fotos y elija **colocar en mundo mezclado**. Una vez que se ha colocado, puedes mover la foto por el mundo.

Para ver y/o guardar sus fotos y videos de realidad mixta en un equipo PC conectado a HoloLens, puede usar [Windows Device portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture) o el [Explorador de archivos de su equipo a través de MTP](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens).

### Usar el explorador de archivos para obtener imágenes, vídeos y archivos

Al igual que con otros dispositivos móviles, conecta tu HoloLens a tu PC para que el explorador de archivos acceda a tus bibliotecas de HoloLens (fotos, videos, documentos) para facilitar la transferencia. Este método es fácil de usar y no requiere el uso de portal de dispositivos o Wi-Fi.

1. Desbloquea el dispositivo.
1. Conecte el dispositivo a un equipo de PC a través de USB.
1. El explorador de archivos debe abrirse en su PC.
1. Vaya a: esta PC\\*yourhololensname*\Internal Storage\Pictures\Camera
1. Copia cualquier archivo que necesites en tu PC.

Sugerencias:
- Si no ves ningún archivo, asegúrate de iniciar sesión en tu HoloLens para permitir el acceso a tus datos.
- Puede obtener otros archivos en otras carpetas, como archivos de [diagnóstico](hololens-diagnostic-logs.md#offline-diagnostics) de la carpeta documentos.
- Desde el explorador de archivos de su PC, puede seleccionar Propiedades de dispositivo para ver el número de versión del SO Windows Holographic (versión del firmware) y el número de serie del dispositivo y el porcentaje de la batería.
- Si su organización ha usado MDM para deshabilitar la [Conectividad/AllowUSBConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) , no podrá conectarse a su dispositivo.

## Comparte tus fotos y vídeos de realidad mixta

Después de capturar una foto o un vídeo de realidad mixta, aparecerá una vista previa. Seleccione el icono **compartir** situado encima de la vista previa para abrir el Asistente para compartir. Desde allí, puedes seleccionar el punto final al que deseas compartir la foto o el vídeo.

También puedes compartir fotos y videos de realidad mixta desde OneDrive, cargando automáticamente tus fotos y videos de realidad mixta. Abre la aplicación de OneDrive en HoloLens e inicia sesión con una [cuenta](https://account.microsoft.com) personal de Microsoft si aún no lo has hecho. Selecciona el icono **configuración** y elige **carga**de la cámara. Activar la carga de la cámara. Ahora, tus fotos y vídeos de realidad mixta se cargarán en OneDrive cada vez que inicies la aplicación en HoloLens.

> [!NOTE]
> Solo puede habilitar la carga de la cámara en OneDrive si ha iniciado sesión en OneDrive con una cuenta personal de Microsoft. Si configura HoloLens con una cuenta profesional o educativa, puede Agregar una cuenta personal de Microsoft en la aplicación de OneDrive para habilitar esta característica.

## Limitaciones de la captura de realidad mixta

- Al usar una captura de realidad mixta, la velocidad de fotogramas de HoloLens será de una mitad de 30 Hz.
- Los vídeos tienen una duración máxima de cinco minutos.
- La resolución de las fotos y los vídeos puede reducirse si otra aplicación ya está usando la foto o la cámara de vídeo, mientras se transmite por secuencias en vivo o cuando los recursos del sistema son bajos.

## Formato de archivo predeterminado y resolución

### Formato de foto y resolución predeterminados

|  Dispositivo  |  Formato  |  Extensión  |  Resolución  |
|----------|----------|----------|----------|
| HoloLens 2 | [JPEG](https://en.wikipedia.org/wiki/JPEG) | . jpg | 3904x2196px |
| HoloLens (1ª generación) | [JPEG](https://en.wikipedia.org/wiki/JPEG) | . jpg | 1408x792px |

### Formato y resolución de video grabados

| Dispositivo | Formato | Extensión | Resolución | Rapidez | Audio |
|----------|----------|----------|----------|----------|----------|
| HoloLens 2 | [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 | 1920x1080px | 30 fps | Estéreo a 48 kHz |
| HoloLens (1ª generación) |  [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 | 1216x684px | 24fps | Estéreo a 48 kHz |
