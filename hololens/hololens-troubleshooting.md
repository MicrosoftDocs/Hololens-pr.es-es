---
title: HoloLens Solución de problemas de dispositivos
description: Manténgase al día de las soluciones más comunes para HoloLens problemas de dispositivos y técnicas de solución de problemas.
author: evmill
ms.author: v-evmill
ms.date: 10/13/2021
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: ranjibb
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: issues, bug, troubleshoot, fix, help, support, HoloLens, emulator
ms.openlocfilehash: deed0d14b2567ae0a1fb2cde8ad1fbe3dbb20bb3
ms.sourcegitcommit: 73a1555fb8b84f3d20c480282c648d8d800a6c98
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/26/2021
ms.locfileid: "130351772"
---
# <a name="device-troubleshooting"></a>Solución de problemas de dispositivos

En este artículo se describe cómo resolver varios problemas HoloLens comunes.

>[!IMPORTANT]
> Antes de iniciar cualquier procedimiento de solución de problemas, asegúrese de que el dispositivo tenga entre un **20 y un 40 por ciento** de batería, si es posible. Las [luces indicadoras de batería](hololens2-setup.md#lights-that-indicate-the-battery-level) que se encuentran debajo del botón de encendido son una manera rápida de comprobar la capacidad de la batería sin iniciar sesión en el dispositivo.

<a id="list"></a>

**Problemas conocidos**
- [Corrección de Insider: cada vez que la alimentación llega al 18 %, el dispositivo se apaga de repente automáticamente.](#every-time-the-power-goes-to-18-percent-the-device-suddenly-shuts-down-automatically)
- [OneDrive La aplicación para UWP no funciona para Azure AD usuarios](#onedrive-uwp-app-doesnt-work-for-azure-ad-users)
- [¿Por qué aparece 0x80180014 durante Autopilot?](#why-do-i-see-0x80180014-during-autopilot)
- [Microsoft Store código de error 0x80131500](#microsoft-store-error-code-0x80131500)
- [Microsoft Edge no se puede iniciar el micrófono](#microsoft-edge-fails-to-start-the-microphone)
- [**Corregido:** Remote Assist vídeo se bloquea después de 20 minutos](#remote-assist-video-freezes-after-20-minutes)
- [Inicio de sesión automático pide inicio de sesión](#auto-login-asks-for-log-in)
- [Microsoft Edge no se puede iniciar](#microsoft-edge-fails-to-launch)
- [El teclado no cambia a caracteres especiales](#keyboard-doesnt-switch-to-special-characters)
- [**Corregido:** al descargar archivos bloqueados no se muestra el error](#downloading-locked-files-doesnt-error)
- [**Corregido:** se Portal de dispositivos de carga o descarga de archivos](#device-portal-file-uploaddownload-times-out)
- [Pantalla azul después de la inscripción de la versión preliminar de Insider en un dispositivo parpadeado con una compilación de Insider](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
- [OneDrive no carga automáticamente imágenes](#onedrive-doesnt-automatically-upload-pictures)

**General**
- [HoloLens no responde o no se inicia](#hololens-is-unresponsive-or-wont-start)
- [Error "Espacio en disco bajo"](#low-disk-space-error)
- [Error de calibración](#calibration-fails)
- [No se puede iniciar sesión porque mi HoloLens se ha configurado previamente para otra persona.](#cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else)
- [Unity no funciona](#unity-isnt-working)
- [Windows Portal de dispositivos no funciona correctamente](#windows-device-portal-isnt-working-correctly)
- [El HoloLens Emulator no funciona](#the-hololens-emulator-isnt-working)

**Entrada**
- [Los comandos de voz no funcionan](#voice-commands-arent-working)
- [La entrada de mano no funciona](#hand-input-isnt-working)

**Conectividad**
- [No se puede conectar a Wi-Fi](#cant-connect-to-wi-fi)

**Dispositivos externos** 
- [Bluetooth dispositivos no están emparejados](#bluetooth-devices-arent-pairing)
- [El micrófono USB-C no funciona](#usb-c-microphone-isnt-working)
- [Los dispositivos que aparecen como Configuración no funcionan](#devices-listed-as-available-in-settings-dont-work)

## <a name="every-time-the-power-goes-to-18-percent-the-device-suddenly-shuts-down-automatically"></a>Cada vez que la alimentación llega al 18 por ciento, el dispositivo se apaga de repente automáticamente

> [!NOTE]
> Hay una corrección para este problema disponible en [Windows Insiders.](hololens-insider.md)

Hay un problema conocido conocido por el que cuando el dispositivo alcanza el 18 % de batería, se apagará inesperadamente. Se trata de un problema de software, no un problema de hardware o batería, por lo que no intercamba dispositivos por esto. Si no está seguro de si el problema coincide con este error, haga lo siguiente:

1. Asegúrese de que los diagnósticos opcionales están habilitados en los dispositivos.
1. Reproducir el problema
1. Envío de un [Centro de opiniones](hololens-feedback.md) problema
1. Compartir la dirección URL del problema de comentarios
1. [Obtener ayuda](https://aka.ms/hololenssupport)

[Volver a la lista](#list)

## <a name="onedrive-uwp-app-doesnt-work-for-azure-ad-users"></a>OneDrive La aplicación para UWP no funciona para Azure AD usuarios

Si usa OneDrive For Business con su cuenta de Azure AD, es posible que haya encontrado un error al iniciar sesión en la bandeja de OneDrive aplicación. No poder iniciar sesión en la aplicación OneDrive no afecta a las cargas automáticas de imágenes y vídeos capturados por la aplicación Cámara. Los archivos todavía se pueden guardar y acceder desde el OneDrive para la Empresa almacenamiento en la nube. Los OneDrive y HoloLens están trabajando en el problema.

### <a name="workarounds"></a>Soluciones alternativas

Requisito previo: los clientes pueden Microsoft Edge y el sistema operativo del dispositivo se actualiza a Windows holographic, compilación 21H1 o posterior.

Si tiene este problema, pruebe una de las siguientes opciones:

- Los usuarios pueden acceder directamente OneDrive For Business desde Microsoft Edge e interactuar con sus archivos en el sitio web desde su explorador.
- Los usuarios pueden instalar OneDrive PWA aplicación para HoloLens descargando desde Microsoft Edge. Esto permitirá que los usuarios vuelvan a ver y administrar archivos en el dispositivo. Lea y siga estas [instrucciones para instalar la OneDrive PWA en su HoloLens.](holographic-store-apps.md#install-microsoft-onedrive-pwa-app)

[Volver a la lista](#list)

## <a name="why-do-i-see-0x80180014-during-autopilot"></a>¿Por qué aparece 0x80180014 durante Autopilot?

Este error suele producirse durante el restablecimiento y el nuevo uso de los flujos en los que un dispositivo HoloLens ha pasado por Autopilot al menos una vez. Para resolver este problema, [](/mem/autopilot/troubleshoot-device-enrollment#error-code-0x80180014-when-re-enrolling-using-self-deployment-or-pre-provisioning-mode) elimine el dispositivo de la Microsoft Intune restablezca de nuevo para completar el flujo de Autopilot.

Para más información, consulte los pasos de [solución de problemas en la página de Autopilot.](hololens2-autopilot.md#issue---mdm-enrollment-fails-with-error-0x80180014-error-code-during-autopilot)

## <a name="microsoft-store-error-code-0x80131500"></a>Microsoft Store código de error 0x80131500

Algunos usuarios pueden experimentar que la Microsoft Store funciona no según lo previsto y ver el código de error 0x80131500. Se trata de un problema causado por la región establecida en el HoloLens no está disponible en la aplicación Microsoft Store en HoloLens. Si encuentra código de error 0x80131500, para solucionarlo, siga estos pasos:

1. Establezca Configuración > hora & idioma > región > país o región, en uno de los siguientes valores:
    - Estados Unidos, Japón, China, Alemania, Canadá, Reino Unido, Irlanda, Francia, Australia, Nueva Zelanda.
1. Reinicie la aplicación Store.
1. Para que todo el dispositivo refleje el cambio, el dispositivo deberá reiniciarse.

El HoloLens está trabajando para agregar compatibilidad con más regiones.

Consulte aquí [los países para comprar HoloLens 2.](hololens2-purchase.md)

## <a name="microsoft-edge-fails-to-start-the-microphone"></a>Microsoft Edge no se puede iniciar el micrófono

Cuando los usuarios Microsoft Edge el micrófono pueden no iniciarse, por lo que no se puede usar para interactuar con Edge en HoloLens. Este problema conocido está relacionado con la versión de la aplicación Microsoft Edge; no vuelva a actualizar el dispositivo a una versión anterior, ya que esto no corregirá este problema.

### <a name="who-is-affected"></a>Quién se ve afectado?

Los usuarios que Microsoft Edge versión 93, 94 o 95.
Puede comprobar qué versión de Microsoft Edge tiene mediante la aplicación Microsoft Store y, a continuación, seleccionar el botón "Ver más" representado por **...** y, a continuación, seleccionar Descargas **y actualizaciones.**

### <a name="work-around"></a>Solución

La corrección actual está en la versión 96, que está disponible para los usuarios que se han inscrito en Microsoft Edge Insiders. Esto es diferente de inscribir el dispositivo como un Windows Insider. Lea estas instrucciones para obtener más información [sobre cómo inscribirse en el programa insider de Edge.](hololens-new-edge.md#microsoft-edge-insider-channels)

## <a name="remote-assist-video-freezes-after-20-minutes"></a>Remote Assist vídeo se bloquea después de 20 minutos

> [!NOTE]
> Hay una versión más reciente de Remote Assist que tiene una corrección para este problema. Actualice [los Remote Assist](holographic-store-apps.md#update-apps) a la versión más reciente para evitar este problema.

> [!NOTE]
> Debido a la gravedad de este problema conocido, hemos pausado temporalmente la disponibilidad de Windows Holographic, versión 21H1. La compilación 21H1 ahora está disponible de nuevo, por lo que los dispositivos pueden actualizarse una vez más a la compilación 21H1 más reciente.

En la versión más reciente de [Windows Holographic, versión 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)algunos usuarios de Remote Assist han experimentado la inmovilización de vídeo durante las llamadas durante más de 20 minutos. Se trata de **un problema conocido.**

### <a name="workarounds"></a>Soluciones alternativas

Si no puede actualizar la versión Remote Assist a una compilación más reciente, pruebe el siguiente trabajo.

#### <a name="restart-in-between-calls"></a>Reinicio entre llamadas

Si las llamadas tienen una duración de 20 minutos y está experimentando este problema, intente reiniciar el dispositivo. Al reiniciar el dispositivo entre Remote Assist llamadas se actualizará el dispositivo y se volverá a poner en un buen estado.

Para reiniciar rápidamente un dispositivo en Windows Holographic, la versión [21H1](hololens-release-notes.md#windows-holographic-version-21h1) abre el menú Inicio y selecciona el icono de usuario y, a continuación, **selecciona Reiniciar**.

[Volver a la lista](#list)

## <a name="auto-login-asks-for-log-in"></a>Inicio de sesión automático pide inicio de sesión

Un HoloLens 2 se puede configurar para iniciar sesión automáticamente a través de las opciones de inicio de sesión de cuentas de **Configuración**  ->    ->    -> y, en Requerido, establecer el valor en **Nunca**. Es posible que algunos usuarios deba iniciar sesión de nuevo en el dispositivo al actualizar un dispositivo con una actualización considerablemente grande, como una actualización de características. Se trata de **un problema conocido.**

Ejemplo de cuándo podría ocurrir:

- Actualización de un dispositivo de Windows Holographic, versión 2004 (compilación 19041.xxxx) a Windows Holographic, versión 21H1 (compilación 20346.xxxx)
- Actualización de un dispositivo para realizar una actualización grande en la misma compilación principal, por ejemplo, Windows Holographic, versión 2004 a Windows Holographic, versión 20H2
- Actualización de un dispositivo de una imagen de fábrica a la imagen más reciente

Esto no debe ocurrir durante:

- Dispositivos que toman una actualización de mantenimiento mensual

Métodos de trabajo:

- Métodos de inicio de sesión como pin, contraseña, iris, autenticación web o claves FIDO2.
- Si no se puede recordar el PIN del dispositivo y no hay otros métodos de autenticación disponibles, un usuario puede usar el [modo de reflashación manual](hololens-recovery.md#manual-flashing-mode-procedure).

[Volver a la lista](#list)

## <a name="microsoft-edge-fails-to-launch"></a>Microsoft Edge no se puede iniciar

> [!NOTE]
> Este problema se creó originalmente con la versión de envío de Microsoft Edge en mente. Este problema se puede resolver en el [nuevo Microsoft Edge](hololens-new-edge.md). Si no es así, envíe sus comentarios.

Algunos clientes han notificado un problema por el Microsoft Edge no se puede iniciar. Para estos clientes, el problema persiste durante el reinicio y no se resuelve con Windows o actualizaciones de la aplicación. Si tiene este problema y ha confirmado que [Windows](hololens-updates.md#manually-check-for-updates)está actualizado, envíe un error desde la aplicación [Centro de opiniones](hololens-feedback.md) con la siguiente categoría y subcategoría: Instalar y actualizar > Descargar, instalar y configurar Windows Update.

No hay soluciones alternativas conocidas, ya que hasta ahora no hemos podido resolver la causa principal del problema. La presentación de un error mediante Centro de opiniones ayudará a nuestra investigación. Se trata de **un problema conocido.**

[Volver a la lista](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a>El teclado no cambia a caracteres especiales

Hay un problema durante la OOBE, donde una vez que el usuario ha elegido una cuenta de trabajo o educativa y escribe su contraseña, intenta cambiar a los caracteres especiales del teclado pulsando el botón &123 no cambia a caracteres especiales. Se trata de **un problema conocido.**

Entornos de trabajo:

- Cierre el teclado y vuelva a abrirlo pulsando en el campo de texto.
- Escriba incorrectamente la contraseña. Cuando el teclado se vuelva a iniciar la próxima vez, funcionará según lo previsto.
- Autenticación web, cierre el teclado y **seleccione Iniciar sesión desde otro dispositivo.**
- Si solo escribe números, un usuario puede presionar y mantener presionadas ciertas teclas para abrir un menú expandido.
- Uso de un teclado USB.

Esto no afecta a:

- Usuarios que deciden usar una cuenta personal.

[Volver a la lista](#list)

## <a name="downloading-locked-files-doesnt-error"></a>No se produce un error al descargar archivos bloqueados

> [!NOTE]
> Se trata de **un problema conocido** que se [corrigió en Windows Holographic, versión 21H1 - Actualización de julio de 2021](hololens-release-notes.md#windows-holographic-version-21h1---july-2021-update).

En compilaciones anteriores de Windows Holographic, al intentar descargar un archivo bloqueado, el resultado sería una página de error HTTP. En la actualización Windows Holographic, versión 21H1, al intentar descargar un archivo bloqueado no ocurre nada visible: el archivo no se descarga y no hay ningún error.

[Volver a la lista](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a>Portal de dispositivos de carga o descarga de archivos
> [!NOTE]
> Se trata de **un problema conocido** que se [corrigió en Windows Holographic, versión 21H1 - Actualización de julio de 2021](hololens-release-notes.md#windows-holographic-version-21h1---july-2021-update). Si anteriormente deshabilitó la conexión SSL como parte de la solución alternativa, se recomienda encarecidamente volver a habilitarla.

Algunos clientes han descubierto que, al intentar cargar o descargar archivos, la operación puede parecer que se ha quedado y, a continuación, se ha completado el tiempo de espera o nunca se ha completado. Esto es independiente[](#downloading-locked-files-doesnt-error) del problema conocido de "archivo bloqueado": esto afecta a las compilaciones en el mercado de Windows Holographic, versiones 2004, 20H2 y 21H1. El problema se ha originado en un error en el control de Portal de dispositivos de determinadas solicitudes y se produce de forma más coherente al usar https, que es el valor predeterminado.

### <a name="workaround"></a>Solución alternativa

Esta solución alternativa, que se aplica igualmente a Wi-Fi y UsbNcm, consiste en deshabilitar la opción "obligatorio" en "Conexión SSL". Para ello, vaya a Portal de dispositivos, **Sistema** y seleccione la **página Preferencias.** En la **sección Seguridad del dispositivo,** busque **Conexión SSL** y desactive para deshabilitar **Requerido.**

A continuación, el usuario debe ir a http://, no https:// (dirección IP) y las características como la carga y descarga de archivos funcionarán.

[Volver a la lista](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a>Pantalla azul después de la inscripción de la versión preliminar de Insider en un dispositivo parpadeado con una compilación de Insider

Se trata de un problema que afecta a los usuarios que se encontraban en una compilación en versión preliminar de Insider, se ha reflashado su HoloLens 2 con una nueva compilación en versión preliminar de Insider y, a continuación, se ha des inscrito en el programa Insider. Se trata de **un problema conocido.**

Esto no afecta a:

- Usuarios que no están inscritos en Windows Insider
- Insiders:
    - Si un dispositivo se ha inscrito desde las compilaciones de Insider, era la versión 18362.x
    - Si se ha publicado una compilación 19041.x firmada por Insider, permanezca inscrito en el programa Insider.

Trabajo:

- Evitar el problema
    - Flash en una compilación que no es de insider. Una de las actualizaciones mensuales normales.
    - Permanecer en la versión preliminar de Insider
- Reflash the device (Volver a actualizar el dispositivo)

    1. Coloque el [HoloLens 2 en modo de parpadeo](hololens-recovery.md) manualmente; para hacerlo, apague completamente sin conectarse. A continuación, mientras mantiene presionado Volumen, pulse el botón De encendido.

    1. Conectar al equipo y abra Advanced Recovery Companion.

    1. Flash el HoloLens 2 a la compilación predeterminada.

[Volver a la lista](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a>OneDrive no carga automáticamente imágenes

La OneDrive aplicación para HoloLens no admite la carga automática de cámaras para cuentas de trabajo o educativas. Se trata de **un problema conocido.**

Soluciones alternativas:

- Si es viable para su empresa, la carga automática de la cámara se admite en las cuentas microsoft de consumidor. Puede iniciar sesión en su cuenta Microsoft además de la cuenta profesional o educativa (la aplicación OneDrive admite el inicio de sesión dual). Desde el perfil de la cuenta Microsoft OneDrive puede habilitar la carga automática de la cámara en segundo plano.

- Si no puede usar de forma segura una cuenta Microsoft de consumidor para cargar las fotos automáticamente, puede cargar manualmente las fotos en su cuenta de trabajo o educativa desde la OneDrive aplicación. Para ello, asegúrese de que ha iniciado sesión en su cuenta de trabajo o educativa en OneDrive aplicación. Seleccione el **+** botón y elija **Upload**. Para buscar las fotos o vídeos que desea cargar, vaya a **Imágenes > Camera Roll**. Seleccione las fotos o vídeos que desea cargar y, a continuación, seleccione el **botón** Abrir.

[Volver a la lista](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a>HoloLens no responde o no se inicia

Si el HoloLens no se iniciará:

- Si los LED situados junto al botón de encendido no se encienden o solo un LED parpadea brevemente, es posible que deba cargar el [HoloLens.](hololens2-charging.md#charging-the-device)
- Si los LED se encienden al presionar el botón de encendido, pero no puede ver nada en las pantallas, realice un restablecimiento de forma fuerte [del dispositivo.](hololens-recovery.md#hard-restart-procedure)

Si el HoloLens se inmoviliza o deja de responder:

- Para desactivar el HoloLens, presione el botón de encendido hasta que los cinco LED se apaguen o durante 15 segundos si los LED no responden. Para iniciar el HoloLens, vuelva a presionar el botón de encendido.

Si estos pasos no funcionan, [](hololens-recovery.md) puede intentar recuperar el HoloLens 2 o HoloLens [(1.ª generación).](hololens1-recovery.md)

[Volver a la lista](#list)

## <a name="low-disk-space-error"></a>Error "Espacio bajo en disco"

Tendrá que liberar espacio de almacenamiento realizando una o varias de las siguientes acciones:

- Elimine algunos espacios no usados. Vaya a **Configuración** Espacios del sistema, seleccione un espacio que ya no necesite  >    >  y, a continuación, **seleccione Quitar**.
- Quite algunos de los hologramas que ha colocado.
- Elimine algunas imágenes y vídeos de la Fotos aplicación.
- Desinstale algunas aplicaciones del HoloLens. En la **lista Todas las** aplicaciones, mantenga presionada la aplicación que desea desinstalar y, a continuación, seleccione **Desinstalar**.

[Volver a la lista](#list)

## <a name="calibration-fails"></a>Error de calibración

La calibración debería funcionar para la mayoría de las personas, pero hay casos en los que se produce un error en la calibración.
  
Entre las posibles razones del error de calibración se incluyen las siguientes:

- Distraerse y no seguir los objetivos de calibración
- Visor de dispositivos o visores de dispositivos desnuciados o rascados que no están correctamente posicionados
- Gafas desnuciadas o rayadas
- Ciertos tipos de lentes de contacto y gafas (lentes de contacto coloreadas, algunas lentes de contacto toréricas, gafas de bloqueo de IR, gafas de sol de alta graduación, gafas de sol o similares)
- Una composición más pronunciada y algunas extensiones de pestañas
- Marcos de gafas gruesas o de vello si impiden que el dispositivo vea los ojos
- Cierta fisonología ocular, condiciones oculares o cáncer de ojo, como ojos estrechos, pestañas largas, ambliopía, nistagmo, algunos casos de LASIK u otras operaciones oculares

Si la calibración no se realiza correctamente, pruebe:

- Limpieza del visor del dispositivo
- Limpieza de las gafas
- Insertar el visor del dispositivo lo más cerca posible de los ojos
- Mover objetos en el visor fuera del camino (por ejemplo, el vello)
- Encender una luz en la habitación o salir de la luz directa

Si ha seguido todas las directrices y la calibración sigue teniendo errores, puede deshabilitar la solicitud de calibración en Configuración. Háganoslo saber también mediante la presentación de [comentarios en Centro de opiniones](hololens-feedback.md).

Consulte también información relacionada para la solución [de problemas de color de imagen o brillo.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)

La configuración de IPD no es aplicable HoloLens 2, ya que el sistema calcula las posiciones de los ojos. 

[Volver a la lista](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a>No se puede iniciar sesión porque mi HoloLens se ha configurado previamente para otra persona.

Puede poner [el dispositivo en modo de **flashing y** usar Advanced Recovery Companion](hololens-recovery.md#clean-reflash-the-device) para recuperar el dispositivo.

[Volver a la lista](#list)


## <a name="unity-isnt-working"></a>Unity no funciona

- Consulte [Instalación de las herramientas](/windows/mixed-reality/install-the-tools) para obtener la versión más actualizada de Unity recomendada para HoloLens desarrollo.
- Los problemas conocidos de Unity HoloLens Technical Preview se documentan en los [foros HoloLens Unity.](https://forum.unity3d.com/threads/known-issues.394627/)

[Volver a la lista](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a>Windows Portal de dispositivos no funciona correctamente

- La característica Live Preview de Mixed Reality captura puede presentar varios segundos de latencia.

- En la página Entrada virtual, los controles Gesto y Desplazamiento de la sección Gestos virtuales no son funcionales. Su uso no tendrá ningún efecto. El teclado virtual de la página de entrada virtual funciona correctamente.

- Después de habilitar el modo de desarrollador Configuración, puede tardar unos segundos antes de que el conmutador active el Portal de dispositivos está habilitado.

[Volver a la lista](#list)

## <a name="the-hololens-emulator-isnt-working"></a>El HoloLens Emulator no funciona

La información sobre HoloLens emulator se encuentra en nuestra documentación para desarrolladores.  Obtenga más información sobre [la solución de problemas HoloLens emulador](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting).


- No todas las aplicaciones del Microsoft Store son compatibles con el emulador. Por ejemplo, Young Conker y Fragments no se pueden reproducir en el emulador.
- No puede usar la cámara web del equipo en el Emulator.
- La característica Live Preview del Windows Portal de dispositivos no funciona con el emulador. Todavía puede capturar vídeos Mixed Reality imágenes.

[Volver a la lista](#list)

## <a name="voice-commands-arent-working"></a>Los comandos de voz no funcionan

Si Cortana no responde a los comandos de voz, asegúrese de Cortana esté activado. En la lista Todas las aplicaciones, seleccione **Cortana**  >  **menú**  >  **Notebook**  >  **Configuración** para realizar cambios. Para más información sobre lo que puede decir, consulte [Uso de la voz con HoloLens](hololens-cortana.md).

En HoloLens (1.ª generación), el reconocimiento de voz integrado no es configurable. Siempre está activado. En HoloLens 2, puede elegir si quiere activar el reconocimiento de voz y Cortana durante la configuración del dispositivo.

Si el HoloLens 2 no responde a su voz, asegúrese de que el reconocimiento de voz está activado. Vaya a **Start Configuración** Privacy Speech (Iniciar voz  >    >  **de**  >  **privacidad)** y active **speech recognition (Reconocimiento de voz).**

[Volver a la lista](#list)

## <a name="hand-input-isnt-working"></a>La entrada de mano no funciona

Para asegurarse de HoloLens puede ver las manos, debe mantenerlas en el marco de gestos.  El Mixed Reality Inicio proporciona comentarios que le permiten saber cuándo se realiza el seguimiento de las manos.  Los comentarios son diferentes en las distintas versiones de HoloLens:

- En HoloLens (1.ª generación), el cursor de mirada cambia de un punto a un anillo.
- En HoloLens 2, aparece un cursor de dedo cuando la mano está cerca de una pizarra y aparece un rayo de mano cuando las pizarras están más lejos

Muchas aplicaciones envolventes siguen patrones de entrada similares a Mixed Reality Inicio.  Obtenga más información sobre el uso de la entrada [HoloLens (1.ª generación)](hololens1-basic-usage.md#use-hololens-with-your-hands) [y HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).

Si va a llevar unas gafas, tenga en cuenta que algunos tipos de gafas no funcionan con el seguimiento de las manos.  Un ejemplo común son los anillos negros, que tienden a absorber la luz de los rayos y no son recogidas por la cámara de profundidad.  Si el trabajo implica una torción, se recomienda probar un color más claro, como azul o gris.  Otro ejemplo es una bolsa grande, que tiende a ocultar la forma de la mano. Se recomienda usar unas gafas que sean lo más apropiadas posible para obtener los mejores resultados.

Si el visor tiene huellas digitales o marcas, use el limpiador de limpieza de microfibras que se incluye con el HoloLens para limpiar la visor de forma descontrolable.

[Volver a la lista](#list)

## <a name="cant-connect-to-wi-fi"></a>No se puede conectar a Wi-Fi

Estas son algunas de las cosas que debe intentar si no puede conectar HoloLens a una red Wi-Fi:

- Asegúrese de que la Wi-Fi está activada. Para comprobarlo, use el gesto Iniciar y, a continuación, **seleccione Configuración**  >  **Red &amp;**  >  **Wi-Fi de Internet.** Si la Wi-Fi está activada, intente desactivarla y volver a activarla.
- Acérquese al enrutador o al punto de acceso.
- Reinicie el enrutador Wi-Fi y, a continuación, [reinicie HoloLens](hololens-recovery.md). Try connecting again (Intente conectarse de nuevo).
- Si ninguna de estas cosas funciona, asegúrese de que el enrutador usa el firmware más reciente. Puede encontrar esta información en el sitio web del fabricante.

[Volver a la lista](#list)

## <a name="bluetooth-devices-arent-pairing"></a>Bluetooth dispositivos no están emparejados

Si tiene problemas para [emparejar un Bluetooth,](hololens-connect-devices.md)pruebe lo siguiente:

- Vaya a **Configuración**  >  **Dispositivos** y asegúrese de que Bluetooth está activado. Si es así, descálala y vuelve a activarla.
- Asegúrese de que el dispositivo Bluetooth está totalmente cargado o tiene baterías nuevas.
- Si todavía no puede conectarse, [reinicie el HoloLens](hololens-recovery.md).

[Volver a la lista](#list)

## <a name="usb-c-microphone-isnt-working"></a>El micrófono USB-C no funciona

Tenga en cuenta que algunos micrófonos USB-C se informan incorrectamente como micrófono *y* como altavoz. Se trata de un problema con el micrófono y no con HoloLens. Al conectar uno de estos micrófonos a HoloLens, se puede perder el sonido. Afortunadamente, hay una corrección simple.  

En **Configuración** sonido del sistema , establezca explícitamente los altavoces integrados (controlador de audio de características  ->    ->   **análogas)** como **el dispositivo predeterminado**. HoloLens recordar esta configuración incluso si el micrófono se quita y se vuelve a conectar más adelante.

![Solución de problemas de micrófonos USB-C.](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a>Los dispositivos que aparecen como Configuración no funcionan

HoloLens (1.ª generación) no admite Bluetooth perfiles de audio. Bluetooth dispositivos de audio, como altavoces y cascos, pueden aparecer como disponibles en HoloLens configuración, pero no se admiten.

HoloLens 2 admite el perfil de audio Bluetooth A2DP para la reproducción estéreo. El Bluetooth hands free que permite la captura de micrófono desde un periférico Bluetooth no se admite en HoloLens 2.

Si tiene problemas para usar un Bluetooth, asegúrese de que es un dispositivo compatible. Entre los dispositivos admitidos se incluyen los siguientes:

- QWERTY en inglés Bluetooth teclados (puede usarlos en cualquier lugar en el que use el teclado holográfico).
- Bluetooth mouse.
- El [HoloLens clic en .](hololens1-clicker.md)

Puede emparejar otros dispositivos BLUETOOTH HID y GBP junto con su HoloLens. Sin embargo, es posible que tenga que instalar las aplicaciones complementarias correspondientes Microsoft Store usar realmente los dispositivos.

[Volver a la lista](#list)
