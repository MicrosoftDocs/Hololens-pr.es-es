---
title: Insider Preview para Microsoft HoloLens
description: Obtenga información sobre cómo empezar a trabajar con compilaciones de Insider y proporcionar comentarios valiosos para nuestra próxima actualización del sistema operativo principal para HoloLens.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 10/19/2021
ms.reviewer: ''
manager: ranjibb
appliesto:
- HoloLens 2
ms.openlocfilehash: 382c979138068ab1d9682ee4e84831accc9e4553
ms.sourcegitcommit: 73a1555fb8b84f3d20c480282c648d8d800a6c98
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/26/2021
ms.locfileid: "130351662"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Insider Preview para Microsoft HoloLens

Le damos la bienvenida a las últimas compilaciones de Insider Preview para HoloLens. Es fácil empezar a trabajar [y proporcionar](hololens-insider.md#start-receiving-insider-builds) comentarios valiosos para nuestra próxima actualización importante del sistema operativo para HoloLens.

## <a name="windows-insider-release-notes"></a>Windows Notas de la versión de Insider

Novedades y en el horizonte de HoloLens? Consulte estas nuevas actualizaciones que se HoloLens.

### <a name="colorblind-mode"></a>Modo daltónico

Se agregó en la compilación 20348.1463 de Insider.

El modo daltónico es una excelente característica que hace que HoloLens sea más accesible. El nuevo modo daltónico se puede encontrar en la aplicación Configuración **en** Configuración  ->  **Accesibilidad**  ->  **de color.** Hay disponibles varios filtros nuevos. Este es un ejemplo visual de algunos de los filtros disponibles.

| Desactivado | Grises | Tripia |
|-----|-----------|------------|
| ![Filtro de color desactivado](images/colorblind-off.png)   | ![Escala de grises de filtro de color](images/colorblind-greyscale.png)         | ![Tripia de filtro de color](images/colorblind-tritanopia.png)          |

### <a name="fixes-and-improvements"></a>Correcciones y mejoras

- Se ha corregido un problema conocido por el que cada vez que la energía llega al [18 %,](hololens-troubleshooting.md#every-time-the-power-goes-to-18-percent-the-device-suddenly-shuts-down-automatically)el dispositivo se apaga de repente automáticamente.
- Mejoras en el modo de plataforma móvil al detectar la dirección hacia abajo.
- Se ha corregido un problema en torno a los diálogos de actualización.
- Se ha actualizado la bandeja Microsoft Edge versión del explorador.
- Se ha corregido un problema por el que al alternar los datos de diagnóstico opcionales no se conservaba la configuración elegida en la página de configuración de telemetría después de un reinicio.
- Se ha corregido un problema por el que los códigos QR no se reconocía cuando se giraban en un ángulo de 45 grados con respecto al dispositivo.

## <a name="start-receiving-insider-builds"></a>Empezar a recibir compilaciones de Insider

> [!NOTE]
> Si no ha actualizado recientemente, reinicie el dispositivo para actualizar el estado y obtener la compilación más reciente.
>
> - El comando de voz "Reiniciar dispositivo" funciona bien.
> - También puede elegir el botón reiniciar en Configuración/Windows Programa Insider.
>
> Hemos tenido un error en el back-end que puede haber encontrado y esto le permitirá volver a realizar el seguimiento.

En un dispositivo HoloLens 2, vaya **a Configuración** Update  >  **& Security**  >  **Windows Programa Insider** y seleccione **Introducción.** Vincule la cuenta que usó para registrarse como Windows Insider.

> [!NOTE]
> Para inscribir el dispositivo en compilaciones de Insider, deberá habilitar la telemetría opcional. Si aún no lo ha hecho, abra la aplicación de Configuración, seleccione Diagnósticos de privacidad & comentarios y, a continuación,  ->   seleccione Datos de **diagnóstico opcionales.**

Windows insider ahora se mueve a Canales. El **anillo** rápido se convertirá en  el canal **de** desarrollo, el  anillo lento se convertirá en el **Canal beta** y el anillo versión preliminar se convertirá en el canal de versión preliminar **de versión preliminar.** Este es el aspecto de esa asignación:

![Windows Explicación de Los canales de Insider.](images/WindowsInsiderChannels.png)

Para obtener más información, vea [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) (Introducción a los canales de Insider) Windows blogs.
A continuación, seleccione Desarrollo activo **de Windows**, elija si desea recibir el canal **de** desarrollo o Canal beta **compilaciones** y revise los términos del programa.
Seleccione **Confirmar > Reiniciar ahora** para finalizar. Una vez reiniciado el dispositivo, vaya a Configuración > Actualizar & seguridad > **Buscar** actualizaciones para obtener la compilación más reciente.

### <a name="update-error-0x80070490-work-around"></a>Actualización de errores 0x80070490 de trabajo

Si se produce un error de actualización 0x80070490 al actualizar en el canal Dev o Beta, pruebe el siguiente trabajo a corto plazo. Implica mover el canal insider, seleccionar la actualización y, a continuación, volver a mover el canal insider.

#### <a name="stage-one---release-preview"></a>Fase uno: versión preliminar

1. Configuración, Actualizar & seguridad, Windows Programa Insider, seleccione **Release Preview Channel (Canal de versión preliminar de versión preliminar).**

2. Configuración, Update & Security, Windows Update, Check **for updates**. Después de la actualización, continúe con la fase dos.

#### <a name="stage-two---dev-channel"></a>Fase dos: Canal de desarrollo

1. Configuración, Actualizar & seguridad, Windows Programa Insider, seleccione **Canal de desarrollo.**

2. Configuración, Update & Security, Windows Update, Check **for updates**.

## <a name="ffu-download-and-flash-directions"></a>Instrucciones de descarga y flash de FFU

Para realizar pruebas con un ffu firmado por un vuelo, primero debe desbloquear el dispositivo en vuelo antes de que se abra el ffu firmado por el vuelo.

1. En pc:
    1. Descargue ffu en el equipo desde [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .

    1. Instale ARC (Advanced Recovery Companion) desde la Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .

1. En HoloLens- Desbloqueo de vuelos: abra **Configuración** Update & Security Windows Programa Insider y, a continuación, regístrese  >    >   y reinicie el dispositivo.

1. Flash FFU: ahora puede flashear el vuelo firmado por FFU mediante ARC.

### <a name="provide-feedback-and-report-issues"></a>Proporcionar comentarios e informar de problemas

Use la [aplicación Centro de opiniones en](hololens-feedback.md) su HoloLens para proporcionar comentarios y notificar problemas. El Centro de opiniones garantiza que se incluye toda la información de diagnóstico necesaria para ayudar a nuestros ingenieros a depurar y resolver rápidamente el problema.  Los problemas con la versión en chino y japonés HoloLens deben notificase de la misma manera.

> [!NOTE]
> Asegúrese de aceptar el mensaje que le pregunta si desea Centro de opiniones acceder a la carpeta Documentos (seleccione **Sí** cuando se le solicite).

## <a name="note-for-developers"></a>Nota para desarrolladores

Le recomendamos que pruebe a desarrollar sus aplicaciones mediante compilaciones insider de HoloLens.  Consulte la documentación [HoloLens developer para](https://developer.microsoft.com/windows/mixed-reality/development) comenzar. Esas mismas instrucciones funcionan con compilaciones de Insider de HoloLens.  Puede usar las mismas compilaciones de Unity Visual Studio que ya usa para el HoloLens desarrollo.

## <a name="stop-receiving-insider-builds"></a>Dejar de recibir compilaciones de Insider

Si ya no quiere recibir compilaciones de Insider de Windows Holographic, puede optar por no recibir cuando [](hololens-recovery.md) HoloLens ejecuta una compilación de producción, o bien puede recuperar el dispositivo mediante advanced recovery Companion para recuperar el dispositivo en una versión que no sea Insider de Windows Holographic.

> [!CAUTION]
> Hay un problema conocido en el que los usuarios que desascriban las compilaciones de Insider Preview después de volver a instalar manualmente una nueva compilación de versión preliminar experimentarían una pantalla azul. Después, deben recuperar manualmente su dispositivo. Para obtener información completa sobre si se vería afectado o no, consulte más información sobre [este problema conocido.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)

Para comprobar que el HoloLens está ejecutando una compilación de producción:

1. Vaya a **Configuración > System > Acerca de** y busque el número de compilación.

1. [Consulte las notas de la versión de los números de compilación de producción.](hololens-release-notes.md)

Para rechazar las compilaciones de Insider:

1. En un HoloLens una compilación de producción, vaya a Configuración > **Update & Security > Windows Programa Insider** y seleccione Stop Insider builds (Detener compilaciones de **Insider).**

1. Siga las instrucciones para rechazar el dispositivo.
