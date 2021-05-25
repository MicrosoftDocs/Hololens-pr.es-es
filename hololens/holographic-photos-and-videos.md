---
title: Captura, grabación y uso compartido de vídeos y fotos de realidad mixta
description: Obtenga información sobre cómo capturar, grabar y ver vídeos y fotos de realidad mixta mediante dispositivos de realidad mixta de HoloLens. Obtenga información sobre cómo compartir a través de Miracast o archivos recopilados.
keywords: hololens, photo, video, capture, mrc, mixed reality capture, photos, camera, miracast, stream, livestream, demo, record
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
ms.openlocfilehash: 178dff5d8a30fdd9c5012e2d14f5d4683d6cc23e
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397506"
---
# <a name="create-mixed-reality-photos-and-videos"></a>Creación de fotos y vídeos de realidad mixta

HoloLens ofrece a los usuarios la experiencia de mezclar el mundo real con el mundo digital.  La captura de realidad mixta (MRC) le permite capturar esa experiencia como una foto o vídeo, o compartir lo que ve con otros usuarios en tiempo real.

La captura de realidad mixta usa un punto de vista en primera persona para que otras personas puedan ver hologramas a medida que los vea. Para un punto de vista de tercera persona, use [la vista de espectador](https://docs.microsoft.com/windows/mixed-reality/spectator-view). La vista del espectador es especialmente útil para las demostraciones.

Aunque es divertido compartir vídeos entre amigos y compañeros, los vídeos también pueden ayudar a enseñar a otras personas a usar una aplicación o a comunicar problemas con aplicaciones y experiencias.

> [!NOTE]
> Si no puede iniciar experiencias de captura de realidad mixta y HoloLens es un dispositivo de trabajo, consulte con el administrador del sistema. El acceso a la cámara se puede restringir a través de la directiva de la empresa.

## <a name="capture-a-mixed-reality-photo"></a>Captura de una foto de realidad mixta

Hay varias maneras de hacer una foto de la realidad mixta en HoloLens. puede usar botones de hardware, voz o el menú Inicio.

### <a name="hardware-buttons-to-take-photos"></a>Botones de hardware para tomar fotos

Para hacer una foto rápida de la vista actual, presione los botones subir y bajar el volumen al mismo tiempo.  Esto es un poco parecido a la versión de HoloLens de una captura de pantalla o una pantalla de impresión.

- [Ubicaciones de botones en HoloLens 2](hololens2-hardware.md)
- [Ubicaciones de botones en HoloLens (1ª generación)](hololens1-hardware.md#hololens-components)

> [!NOTE]
> Al mantener **presionados los botones** **subir y** bajar el volumen durante tres segundos, se iniciará la grabación de un vídeo en lugar de tomar una foto. Para detener la grabación, pulse **los botones subir y** bajar **volumen** simultáneamente.

### <a name="voice-commands-to-take-photos"></a>Comandos de voz para tomar fotos

En HoloLens 2, versión 2004 (y posteriores), diga: "Tome una foto".

En HoloLens (1.ª generación) o HoloLens 2, versión 1903, diga: "Hola Cortana, tome una foto".

### <a name="start-menu-to-take-photos"></a>menú Inicio tomar fotos

Use el gesto Iniciar para ir a **Inicio** y, a continuación, seleccione el **icono Cámara.**

Apunte la cabeza en la dirección de lo que desea capturar y, a continuación, pulse [en](hololens2-basic-usage.md#touch-holograms-near-you) el aire para tomar una foto. Puede seguir pulsando en el aire y capturando fotos adicionales. Las fotos que capture se guardarán en el dispositivo.

Use de nuevo el gesto Iniciar para finalizar la captura de fotos.  

## <a name="capture-a-mixed-reality-video"></a>Captura de un vídeo de realidad mixta

Hay varias maneras de grabar un vídeo de realidad mixta en HoloLens. puede usar botones de hardware, voz o el menú Inicio.

### <a name="hardware-buttons-to-record-videos"></a>Botones de hardware para grabar vídeos

La manera más rápida de grabar un  vídeo es  mantener presionados los botones subir y bajar el volumen simultáneamente hasta que comience una cuenta atrás de tres segundos. Para detener la grabación, pulse ambos botones simultáneamente.

> [!NOTE]
> Al presionar rápidamente los **botones subir** **y** bajar volumen al mismo tiempo, se tomará una foto en lugar de grabar un vídeo.

### <a name="voice-to-record-videos"></a>Voz para grabar vídeos

En HoloLens 2, versión 2004 (y posteriores), diga: "Iniciar grabación". Para detener la grabación, diga "Detener grabación".

En HoloLens (1ª generación) o HoloLens 2, versión 1903, diga: "Hola Cortana, empiece a grabar". Para detener la grabación, diga "Hola Cortana, detenga la grabación".

### <a name="start-menu-to-record-videos"></a>menú Inicio grabar vídeos

Use el gesto Iniciar para ir **a Inicio y,** a continuación, seleccione el **icono Vídeo.** Apunte la cabeza en la dirección de lo que desea capturar y, a continuación, pulse [en](hololens2-basic-usage.md#touch-holograms-near-you) el aire para iniciar la grabación. Habrá una cuenta atrás de tres segundos y comenzará la grabación.

Para detener la grabación, use el gesto Iniciar y seleccione el icono **Vídeo** resaltado. El vídeo se guardará en el dispositivo.

> [!NOTE]
> **Solo se aplica a HoloLens (1ª generación)**  
> El [Actualización de octubre de 2018 de Windows 10](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018) cambia cómo se comportan el gesto De inicio y el botón de Windows en HoloLens (1ª generación). Antes de la actualización, el gesto Iniciar o el botón Windows detendría una grabación de vídeo. Sin embargo, después de la actualización, el gesto Iniciar  o el botón De Windows abren el menú Inicio  (o el menú acciones rápidas si se encuentra en una aplicación inmersiva), desde el que puede seleccionar el icono de vídeo resaltado para detener la grabación. 

## <a name="share-what-you-see-in-real-time"></a>Compartir lo que se ve en tiempo real

Puede compartir lo que ve en HoloLens con amigos y compañeros en tiempo real. Hay algunos métodos disponibles:

1. Conectarse a un adaptador o dispositivo habilitado para Miracast para verlo en un televisor.
1. Uso [Portal de dispositivos Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) para verlo en un equipo
1. Uso de [Microsoft HoloLens aplicación complementaria para](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) verlo en un equipo.
1. La implementación de [la aplicación Dynamics 365 Remote Assist](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist) Microsoft, que permite a los trabajadores de primera línea transmitir lo que ven a un experto remoto. A continuación, el experto remoto puede guiar al trabajador de front-line verbalmente o anotando en su mundo.

> [!NOTE]
> Compartir lo que ve a través Portal de dispositivos Windows o Microsoft HoloLens aplicación complementaria requiere que HoloLens esté en [modo de desarrollador.](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)

### <a name="stream-video-with-miracast"></a>Transmisión de vídeo con Miracast

Use el gesto Iniciar para ir a **Inicio** y, a continuación, seleccione el **icono** Conectar. En el selector que aparece, seleccione el dispositivo o adaptador habilitado para Miracast al que desea conectarse.

Para dejar de compartir, use el gesto Iniciar y seleccione el icono **Conectar** resaltado. Dado que estaba transmitiendo, no se guardará nada en el dispositivo.

> [!NOTE]
> La compatibilidad con Miracast se ha habilitado en HoloLens (1.ª generación) a partir [del Actualización de octubre de 2018 de Windows 10](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018).

### <a name="real-time-video-with-windows-device-portal"></a>Vídeo en tiempo real con Portal de dispositivos Windows

Dado que el uso compartido a través de Portal de dispositivos Windows requiere que el modo de desarrollador esté habilitado en HoloLens, siga las instrucciones de nuestra documentación para desarrolladores para configurar el modo de desarrollador y [Portal de dispositivos Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).

### <a name="microsoft-hololens-companion-app"></a>Microsoft HoloLens aplicación complementaria

Dado que el uso compartido Microsoft HoloLens través de la aplicación complementaria de Microsoft HoloLens requiere que el modo de desarrollador esté habilitado en HoloLens, siga las instrucciones de nuestra documentación para desarrolladores para configurar [el modo de desarrollador](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal). A continuación, [descargue Microsoft HoloLens aplicación complementaria y](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) siga las instrucciones de la aplicación para conectarse a HoloLens.

Una vez configurada la aplicación con HoloLens, seleccione la opción Streaming en **vivo** en el menú principal de la aplicación.

## <a name="view-your-mixed-reality-photos-and-videos"></a>Visualización de fotos y vídeos de realidad mixta

Las fotos y vídeos de realidad mixta se guardan en el "camera roll" del dispositivo. Puede examinar el contenido de esta carpeta en HoloLens con la aplicación Explorador de archivos (vaya a **Imágenes > de la cámara).**

También puede ver sus fotos y vídeos de realidad mixta en la aplicación Fotos, que está preinstalada en HoloLens. Para anclar una foto en su mundo, selecciónelo en la aplicación Fotos y elija **Colocar en el mundo mixto.** Puede mover la foto por todo el mundo después de colocarla.

Para ver o guardar sus fotos y vídeos de realidad mixta en un [](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture) equipo conectado a HoloLens, puede usar Portal de dispositivos Windows o el equipo Explorador de archivos a través de [MTP.](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens)

### <a name="use-file-explorer-to-get-your-pictures-videos-and-files"></a>Use Explorador de archivos para obtener imágenes, vídeos y archivos

De forma similar a otros dispositivos móviles, conecte holoLens al equipo para que Explorador de archivos acceda a las bibliotecas de HoloLens (fotos, vídeos, documentos) para facilitar la transferencia. Este método es fácil de usar y no requiere el uso del portal de dispositivos o wi-Fi.

1. Desbloquee el dispositivo.
1. Conecte el dispositivo a un equipo a través de USB.
1. Explorador de archivos debe abrirse en el equipo.
1. Vaya a: \\ *Yourhololensname de este* equipo \Internal Storage\Pictures\Camera Roll
1. Copie los archivos que necesite en el equipo.

Sugerencias:
- Si no ve ningún archivo, asegúrese de iniciar sesión en HoloLens para habilitar el acceso a los datos.
- Puede obtener otros archivos en otras [carpetas,](hololens-diagnostic-logs.md#offline-diagnostics) como los archivos de diagnóstico de la carpeta Documentos.
- Desde Explorador de archivos en el equipo, puede seleccionar Propiedades del dispositivo para ver el número de versión del sistema operativo Windows Holographic (versión de firmware), el número de serie del dispositivo y el porcentaje de batería.
- Si su organización ha usado MDM para deshabilitar [Connectivity/AllowUSBConnection,](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) no podrá conectarse al dispositivo.

## <a name="share-your-mixed-reality-photos-and-videos"></a>Compartir fotos y vídeos de realidad mixta

Antes de [Windows Holographic, versión 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)después de capturar una foto o vídeo de realidad mixta, aparecerá una vista previa. Seleccione el **icono Compartir** situado encima de la versión preliminar para abrir el asistente para compartir. Desde allí, puede seleccionar el punto final con el que desea compartir esa foto o vídeo.

Con Windows Holographic, versión 21H1, después de capturar una foto o un vídeo de realidad mixta, aparecerá una vista previa. Seleccione el **icono Compartir** situado encima de la versión preliminar para abrir el asistente para compartir. Desde allí, puede seleccionar el punto final (Mail, OneDrive, etc.) con el que desea compartir esa foto o vídeo. También puede permitir que HoloLens se comparta con dispositivos cercanos si va a Configuración **-> Sistema -> Experiencias compartidas.** Para obtener más información, lea [Compartir cosas con dispositivos cercanos en Windows 10](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9).

> [!TIP] 
> También puede compartir fotos y vídeos de realidad mixta desde OneDrive cargando automáticamente sus fotos y vídeos de realidad mixta. Abra la aplicación OneDrive en HoloLens e inicie sesión con una cuenta **[microsoft](https://account.microsoft.com)personal,** si aún no lo ha hecho. Seleccione el icono **Configuración** y elija Cargar **cámara.** Active la carga de la cámara. Ahora, las fotos y los vídeos de realidad mixta se cargarán en OneDrive cada vez que inicie la aplicación en HoloLens.

> [!NOTE]
> Solo puede habilitar la carga de cámara en OneDrive si ha iniciado sesión en OneDrive con una cuenta personal de Microsoft. Si configura HoloLens con una cuenta profesionales o educativas, puede agregar una cuenta personal de Microsoft en la aplicación OneDrive para habilitar esta característica.

## <a name="limitations-of-mixed-reality-capture"></a>Limitaciones de la captura de realidad mixta

- Al usar la captura de realidad mixta, la velocidad de fotogramas de HoloLens se reducirá a la mitad a 30 Hz.
- La resolución de fotos y vídeos puede reducirse si otra aplicación ya está utilizando la cámara de fotos o vídeos, mientras que el streaming en vivo o cuando los recursos del sistema son bajos.

### <a name="maximum-recording-length"></a>Longitud máxima de grabación

En HoloLens 2 dispositivos anteriores a Windows Holographic, versión 20H2, los vídeos grabados en el dispositivo se limitaban a una duración máxima de cinco minutos.

Debido a los comentarios de los clientes, hemos aumentado la longitud de grabación de las capturas [de realidad mixta.](holographic-photos-and-videos.md) Las capturas de realidad mixta ya no se limitarán a 5 minutos de forma predeterminada, sino que calcularán la longitud máxima de grabación en función del espacio en disco disponible. El dispositivo calculará la duración máxima de la grabación de vídeo en función del espacio en disco disponible hasta el 80 % del espacio total en disco.

> [!NOTE]
> HoloLens usará una duración de grabación de vídeo predeterminada (5 minutos) si se produce una de las siguientes situaciones:
> - La duración máxima estimada de la grabación es menor que los 5 minutos predeterminados.
> - El espacio en disco disponible es inferior al 20 % del espacio total en disco.

## <a name="default-file-format-and-resolution"></a>Resolución y formato de archivo predeterminados

### <a name="default-photo-format-and-resolution"></a>Resolución y formato de foto predeterminados

|  Dispositivo  |  Formato  |  Extensión  |  Solución  |
|----------|----------|----------|----------|
| HoloLens 2 | [Jpeg](https://en.wikipedia.org/wiki/JPEG) | .jpg | 3904x2196px |
| HoloLens (1.ª generación) | [Jpeg](https://en.wikipedia.org/wiki/JPEG) | .jpg | 1408x792px |

### <a name="recorded-video-format-and-resolution"></a>Resolución y formato de vídeo grabado

| Dispositivo | Formato | Extensión | Solución | Velocidad | Audio |
|----------|----------|----------|----------|----------|----------|
| HoloLens 2 | [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 | 1920x1080px | 30fps | Estéreo de 48 kHz |
| HoloLens (1.ª generación) |  [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 | 1216x684px | 24fps | Estéreo de 48 kHz |
