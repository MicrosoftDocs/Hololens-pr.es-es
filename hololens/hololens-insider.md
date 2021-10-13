---
title: Insider Preview para Microsoft HoloLens
description: Obtenga información sobre cómo empezar a trabajar con las compilaciones de Insider y proporcionar comentarios valiosos sobre nuestra próxima actualización principal del sistema operativo para HoloLens.
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
ms.date: 10/12/2021
ms.reviewer: ''
manager: ranjibb
appliesto:
- HoloLens 2
ms.openlocfilehash: 080eb5949bc80d1ce922d57f099c375668f5633f
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924357"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Insider Preview para Microsoft HoloLens

Le damos la bienvenida a las últimas compilaciones de Insider Preview para HoloLens. Es fácil empezar a trabajar [y proporcionar](hololens-insider.md#start-receiving-insider-builds) comentarios valiosos para la próxima actualización importante del sistema operativo para HoloLens.

## <a name="windows-insider-release-notes"></a>Windows Notas de la versión de Insider

Nos complace que todas nuestras características recientes de Insider se han hecho públicas. Si desea leer sobre ellos, consulte la página de notas [de la versión.](hololens-release-notes.md)

## <a name="start-receiving-insider-builds"></a>Empezar a recibir compilaciones de Insider

> [!NOTE]
> Si no se ha actualizado recientemente, reinicie el dispositivo para actualizar el estado y obtener la compilación más reciente.
>
> - El comando de voz "Reiniciar dispositivo" funciona bien.
> - También puede elegir el botón reiniciar en Configuración/Windows Programa Insider.
>
> Hemos tenido un error en el back-end que es posible que haya encontrado y esto le permitirá volver a realizar el seguimiento.

En un HoloLens 2, vaya **a** Configuración  >  **Update & Security**  >  **Windows Programa Insider** y seleccione **Introducción.** Vincule la cuenta que usó para registrarse como Windows Insider.

> [!NOTE]
> Para inscribir el dispositivo en compilaciones de Insider, deberá habilitar la telemetría opcional. Si aún no lo ha hecho, abra la aplicación de Configuración, seleccione Privacy Diagnostics & feedback (Diagnósticos de privacidad) y, a continuación, seleccione Optional diagnostics data (Datos  ->   de **diagnóstico opcionales).**

Windows insider se está moviendo a Canales. El **anillo** rápido se convertirá en  el canal **de desarrollo,** el  anillo lento se convertirá en el **Canal beta** y el anillo versión preliminar se convertirá en el canal de versión preliminar de **versión preliminar.** Este es el aspecto de esa asignación:

![Windows Explicación de los canales de Insider.](images/WindowsInsiderChannels.png)

Para obtener más información, vea [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) (Introducción a los canales de Insider) Windows blogs.
A continuación, seleccione Desarrollo activo **de Windows**, elija si desea recibir canal **de** desarrollo o Canal beta **compilaciones** y revise los términos del programa.
Seleccione **Confirmar > Reiniciar ahora** para finalizar. Una vez reiniciado el dispositivo, vaya a Configuración > **Update & Security > Check for updates** to get the latest build (Buscar actualizaciones para obtener la compilación más reciente).

### <a name="update-error-0x80070490-work-around"></a>Actualización del 0x80070490 de trabajo

Si se produce un error de actualización 0x80070490 al actualizar en el canal Dev o Beta, pruebe el siguiente trabajo a corto plazo. Implica mover el canal insider, seleccionar la actualización y, a continuación, volver a mover el canal insider.

#### <a name="stage-one---release-preview"></a>Fase uno: versión preliminar

1. Configuración, Actualizar & Seguridad, Windows Programa Insider, seleccione Release **Preview Channel (Canal de versión preliminar de versión preliminar).**

2. Configuración, Update & Security, Windows Update, Check **for updates**. Después de la actualización, continúe con la fase dos.

#### <a name="stage-two---dev-channel"></a>Fase dos: Canal de desarrollo

1. Configuración, Actualizar & seguridad, Windows Programa Insider, seleccione **Canal de desarrollo.**

2. Configuración, Update & Security, Windows Update, Check **for updates**.

## <a name="ffu-download-and-flash-directions"></a>Instrucciones de descarga y flash de FFU

Para probar con un vuelo firmado con ffu, primero debe desbloquear el dispositivo antes de parpadear el vuelo firmado ffu.

1. En pc:
    1. Descargue ffu en el equipo desde [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .

    1. Instale ARC (Advanced Recovery Companion) desde la Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .

1. En HoloLens- Desbloqueo de vuelos: abra **Configuración** Update & Security Windows Programa Insider  >  **y,** a continuación, regístrese y reinicie el  >   dispositivo.

1. Flash FFU: ahora puede flashear el vuelo firmado con FFU mediante ARC.

### <a name="provide-feedback-and-report-issues"></a>Proporcionar comentarios e informar de problemas

Use la [aplicación Centro de opiniones en](hololens-feedback.md) su HoloLens para proporcionar comentarios e informar sobre problemas. El Centro de opiniones garantiza que se incluye toda la información de diagnóstico necesaria para ayudar a nuestros ingenieros a depurar y resolver rápidamente el problema.  Los problemas con la versión en chino y japonés de HoloLens deben informarse de la misma manera.

> [!NOTE]
> Asegúrese de aceptar el mensaje que le pregunta si desea Centro de opiniones acceso a la carpeta Documentos (seleccione **Sí** cuando se le solicite).

## <a name="note-for-developers"></a>Nota para desarrolladores

Le recomendamos que pruebe a desarrollar sus aplicaciones mediante compilaciones insider de HoloLens.  Consulte la documentación [HoloLens developer para](https://developer.microsoft.com/windows/mixed-reality/development) empezar. Esas mismas instrucciones funcionan con compilaciones de Insider de HoloLens.  Puede usar las mismas compilaciones de Unity y Visual Studio que ya usa para el HoloLens desarrollo.

## <a name="stop-receiving-insider-builds"></a>Dejar de recibir compilaciones de Insider

Si ya no quiere recibir compilaciones de Insider de Windows Holographic, puede optar por no recibir cuando [](hololens-recovery.md) HoloLens ejecuta una compilación de producción, o bien puede recuperar el dispositivo mediante Advanced Recovery Companion para recuperar el dispositivo en una versión que no sea Insider de Windows Holographic.

> [!CAUTION]
> Hay un problema conocido en el que los usuarios que no se inscriban en las compilaciones de Insider Preview después de volver a instalar manualmente una nueva compilación de versión preliminar experimentarían una pantalla azul. Después, deben recuperar manualmente su dispositivo. Para obtener información completa sobre si se vería afectado o no, consulte más información sobre [este problema conocido.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)

Para comprobar que el HoloLens está ejecutando una compilación de producción:

1. Vaya a **Configuración > System > Acerca de** y busque el número de compilación.

1. [Consulte las notas de la versión de los números de compilación de producción.](hololens-release-notes.md)

Para no participar en las compilaciones de Insider:

1. En un HoloLens una compilación de producción, vaya a **Configuración > Update & Security > Windows Programa Insider** y seleccione Detener compilaciones de **Insider.**

1. Siga las instrucciones para no participar en el dispositivo.
