---
title: Versión preliminar de Insider para Microsoft HoloLens
description: Obtenga información sobre cómo empezar a trabajar con compilaciones de Insider y proporcionar comentarios valiosos para nuestra próxima actualización principal del sistema operativo para HoloLens.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 8545b5f23dc81c194b68ea8b40feb83e525dfdf7
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397826"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Versión preliminar de Insider para Microsoft HoloLens

Le damos la bienvenida a las últimas compilaciones de Insider Preview para HoloLens. Es fácil empezar a trabajar [y proporcionar](hololens-insider.md#start-receiving-insider-builds) comentarios valiosos para nuestra próxima actualización importante del sistema operativo para HoloLens.

## <a name="windows-insider-release-notes"></a>Windows Insider notas de la versión

Nos complace empezar a pasar nuevas características a Windows Insiders de nuevo. Las nuevas compilaciones pasarán a los canales de desarrollo y beta para las actualizaciones más recientes. Seguiremos actualizando esta página a medida que agreguemos más características y actualizaciones a nuestras Windows Insider compilaciones. Prepárese para mezclar estas actualizaciones en su realidad. 

### <a name="onedrive-for-work-or-school-camera-roll-upload"></a>OneDrive para la carga de la cámara de trabajo o educativa

*Introducido en la compilación 20346.1402*

Hemos agregado una nueva característica a la aplicación configuración de HoloLens 2, que permite a los clientes cargar automáticamente fotos y vídeos de realidad mixta desde la carpeta Imágenes de > Camera Roll del dispositivo a la carpeta OneDrive para trabajo o escuela correspondiente. Esta característica soluciona una brecha de características dentro de la aplicación [OneDrive](holographic-photos-and-videos.md#share-your-mixed-reality-photos-and-videos) en HoloLens 2, que solo admite la carga automática de camera roll en la cuenta microsoft personal de un cliente (y no en su cuenta de trabajo o educativa).

**Funcionamiento**

- Visite **Configuración > system > Cámara de realidad mixta** para habilitar la "carga de la cámara".
- Al establecer esta  característica en la posición En, las fotos o vídeos de realidad mixta capturados en el dispositivo se pondrán automáticamente en cola para cargarse en la carpeta Imágenes > Camera Roll de su cuenta de OneDrive para el trabajo o la escuela.
    >[!NOTE]
    >Las fotos y los vídeos  capturados antes de habilitar esta característica no se pondrán en cola para la carga y seguirán teniendo que cargarse manualmente.
- Un mensaje de estado en la página Configuración mostrará el número de archivos pendientes de carga (o leerá "OneDrive está actualizado" cuando se han cargado todos los archivos pendientes).
- Si le preocupa el ancho de banda o quiere "pausar" la carga por cualquier motivo, puede cambiar la característica a la **posición Desactivado.** Deshabilitar temporalmente la característica garantiza que la cola de carga seguirá aumentando a medida que agregue nuevos archivos a la carpeta Camera Roll, pero los archivos no se cargarán hasta que vuelva a habilitar la característica.
- Los archivos más nuevos se cargarán primero (último en, primero en salir).
- Si la cuenta de OneDrive tiene problemas (por  ejemplo, después de cambiar la contraseña), aparecerá un botón Corregir ahora en la página Configuración.
- No hay ningún tamaño máximo de archivo, pero tenga en cuenta que los archivos grandes tardan más tiempo en cargarse (especialmente si el ancho de banda de carga está restringido). Si "pausa" o desactiva la carga mientras se carga un archivo grande, la carga se cancelará inmediatamente. La carga se reiniciará cuando vuelva a habilitar la característica. no perderá ningún archivo, pero se descartará la carga parcial.

**Problemas conocidos y advertencias**

- Esta configuración no tiene ninguna limitación integrada en función del uso actual del ancho de banda. Si necesita maximizar el ancho de banda para otro escenario, desactive la configuración manualmente. La carga se pausará, pero la característica seguirá supervisando los archivos recién agregados a Camera Roll. Vuelva a habilitar la carga cuando esté listo para que continúe.
- Esta característica debe estar habilitada para cada cuenta de usuario del dispositivo y solo puede cargar archivos de forma activa para el usuario que ha iniciado sesión actualmente en el dispositivo.
- Si va a tomar fotos o vídeos mientras observa el recuento de cargas en la página Configuración en tiempo real, tenga en cuenta que es posible que el recuento de archivos pendientes no cambie hasta que se haya completado la carga del archivo actual.
- La carga se pausará si el dispositivo se queda apagado o está apagado. Para asegurarse de que las cargas pendientes se completan, use activamente el dispositivo hasta que la página Configuración lea "OneDrive está actualizado" o ajuste la configuración de suspensión de **Power &.**

## <a name="start-receiving-insider-builds"></a>Empezar a recibir compilaciones de Insider
> [!NOTE]
> Si no se ha actualizado recientemente, reinicie el dispositivo para actualizar el estado y obtener la compilación más reciente.
> - El comando de voz "Reiniciar dispositivo" funciona bien. 
> - También puede elegir el botón reiniciar en Configuración/Programa Windows Insider.
>
> Hemos tenido un error en el back-end que puede haber encontrado y esto le permitirá volver a realizar el seguimiento.

En un dispositivo HoloLens 2, vaya a **Configuración** Actualizar &  >  **seguridad**  >  **Programa Windows Insider** y seleccione **Introducción.** Vincule la cuenta que usó para registrarse como Windows Insider.
Windows Insider ahora se mueve a Canales. El **anillo** rápido se convertirá en  el canal  **de** desarrollo, el  anillo lento se convertirá en el Canal beta y el anillo versión preliminar se convertirá en el canal de versión preliminar **de versión preliminar.** Este es el aspecto de esa asignación: Windows Insider Channels explanation (Explicación de canales de Windows Insider) Para obtener más información, consulte ![ ](images/WindowsInsiderChannels.png) [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs (Introducción a los canales de Windows Insider en blogs de Windows).
A continuación, seleccione Desarrollo activo de **Windows,** elija si desea recibir canal **de desarrollo** o Canal beta **compilaciones** y revise los términos del programa.
Seleccione **Confirmar > Reiniciar ahora** para finalizar. Una vez reiniciado el dispositivo, vaya a Configuración **> actualizar** & seguridad > Buscar actualizaciones para obtener la compilación más reciente.
### <a name="update-error-0x80070490-work-around"></a>Actualización de errores 0x80070490 de trabajo
Si se produce un error de actualización 0x80070490 al actualizar en el canal Dev o Beta, pruebe el siguiente trabajo a corto plazo. Implica mover el canal insider, seleccionar la actualización y, a continuación, volver a mover el canal insider.
#### <a name="stage-one---release-preview"></a>Fase uno: versión preliminar
1.  Configuración, Actualizar & seguridad, Programa Windows Insider, seleccione **Release Preview Channel (Canal de versión preliminar).**
2.  Settings, Update & Security, Windows Update, **Check for updates**. Después de la actualización, continúe con la fase dos.
#### <a name="stage-two---dev-channel"></a>Fase dos: Canal de desarrollo
1. Configuración, Actualizar & seguridad, Programa Windows Insider, seleccione **Canal de desarrollo**.
2. Configuración, Actualizar & seguridad, Windows Update, **Buscar actualizaciones.**
## <a name="ffu-download-and-flash-directions"></a>Instrucciones de descarga y flash de FFU
Para probar con un vuelo firmado con ffu, primero debe desbloquear el dispositivo antes de parpadear el vuelo firmado ffu.
1. En pc:
    1. Descargue ffu en el equipo desde [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .
    
    1. Instale ARC (Advanced Recovery Companion) desde la Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .
    
1. En HoloLens - Desbloqueo de vuelos: abra La actualización de & seguridad Programa Windows Insider  >    >  **y, a continuación,** regístrese y reinicie el dispositivo.
1. Flash FFU: ahora puede flashear el vuelo firmado con FFU mediante ARC.
### <a name="provide-feedback-and-report-issues"></a>Proporcionar comentarios e informar de problemas
Use la [aplicación Centro de opiniones en](hololens-feedback.md) HoloLens para proporcionar comentarios y notificar problemas. El Centro de opiniones garantiza que se incluye toda la información de diagnóstico necesaria para ayudar a nuestros ingenieros a depurar y resolver rápidamente el problema.  Los problemas con la versión en chino y japonés de HoloLens deben informarse de la misma manera.
> [!NOTE]
> Asegúrese de aceptar el mensaje que le pregunta si desea Centro de opiniones acceso a la carpeta Documentos **(seleccione Sí cuando** se le solicite).
## <a name="note-for-developers"></a>Nota para desarrolladores
Le recomendamos que pruebe a desarrollar sus aplicaciones mediante las compilaciones de Insider de HoloLens.  Consulte la documentación [para desarrolladores de HoloLens](https://developer.microsoft.com/windows/mixed-reality/development) para empezar. Esas mismas instrucciones funcionan con las compilaciones de Insider de HoloLens.  Puede usar las mismas compilaciones de Unity y Visual Studio que ya usa para el desarrollo de HoloLens.
## <a name="stop-receiving-insider-builds"></a>Dejar de recibir compilaciones de Insider
Si ya no quiere recibir compilaciones de Insider de Windows Holographic, puede optar por no [](hololens-recovery.md) recibir cuando HoloLens ejecuta una compilación de producción o puede recuperar el dispositivo mediante Advanced Recovery Companion para recuperar el dispositivo en una versión que no sea Insider de Windows Holographic.
> [!CAUTION]
> Hay un problema conocido en el que los usuarios que no se inscriban en las compilaciones de Insider Preview después de volver a instalar manualmente una nueva compilación de versión preliminar experimentarían una pantalla azul. Después, deben recuperar manualmente su dispositivo. Para obtener información completa sobre si se vería afectado o no, consulte más información sobre [este problema conocido.](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)
Para comprobar que HoloLens ejecuta una compilación de producción:
1. Vaya a **Configuración > sistema > Acerca de** y busque el número de compilación.
1. [Consulte las notas de la versión de los números de compilación de producción.](hololens-release-notes.md)
Para rechazar las compilaciones de Insider:
1. En un dispositivo HoloLens que ejecuta una compilación de producción, vaya a Configuración **> Update & Security > Programa Windows Insider** y seleccione Stop Insider builds (Detener compilaciones de **Insider).**
1. Siga las instrucciones para rechazar el dispositivo.
