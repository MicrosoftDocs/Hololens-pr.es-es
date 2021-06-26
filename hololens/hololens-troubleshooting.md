---
title: Solución de problemas de dispositivos HoloLens
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
keywords: issues, bug, troubleshoot, fix, help, support, HoloLens, emulator
ms.openlocfilehash: b69dddf04ac31b69f0b2f8759d095806189f33ab
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924628"
---
# <a name="device-troubleshooting"></a>Solución de problemas de dispositivos

En este artículo se describe cómo resolver varios problemas comunes de HoloLens.

>[!IMPORTANT]
> Antes de iniciar cualquier procedimiento de solución de problemas, asegúrese de que el dispositivo se cobra entre **el 20 y el 40** por ciento de la capacidad de la batería, si es posible. Las [luces indicadoras de batería](hololens2-setup.md#lights-that-indicate-the-battery-level) ubicadas bajo el botón de encendido son una manera rápida de comprobar la capacidad de la batería sin iniciar sesión en el dispositivo.

<a id="list"></a>

**Problemas conocidos**
- [Remote Assist vídeo se bloquea después de 20 minutos](#remote-assist-video-freezes-after-20-minutes)
- [Inicio de sesión automático pide inicio de sesión](#auto-login-asks-for-log-in)
- [Microsoft Edge no se puede iniciar](#microsoft-edge-fails-to-launch)
- [El teclado no cambia a caracteres especiales](#keyboard-doesnt-switch-to-special-characters)
- [La descarga de archivos bloqueados no muestra el error](#downloading-locked-files-doesnt-error)
- [Portal de dispositivos de carga y descarga de archivos](#device-portal-file-uploaddownload-times-out)
- [Pantalla azul después de la inscripción de la versión preliminar de Insider en un dispositivo parpadeado con una compilación de Insider](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
- [OneDrive no carga automáticamente imágenes](#onedrive-doesnt-automatically-upload-pictures)

**General**
- [HoloLens no responde o no se inicia](#hololens-is-unresponsive-or-wont-start)
- [Error "Espacio en disco bajo"](#low-disk-space-error)
- [Error de calibración](#calibration-fails)
- [No se puede iniciar sesión porque mi HoloLens se ha configurado previamente para otra persona.](#cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else)
- [Unity no funciona](#unity-isnt-working)
- [Portal de dispositivos Windows no funciona correctamente](#windows-device-portal-isnt-working-correctly)
- [El emulador de HoloLens no funciona](#the-hololens-emulator-isnt-working)

**Entrada**
- [Los comandos de voz no funcionan](#voice-commands-arent-working)
- [La entrada de mano no funciona](#hand-input-isnt-working)

**Conectividad**
- [No se puede conectar a Wi-Fi](#cant-connect-to-wi-fi)

**Dispositivos externos** 
- [Los dispositivos Bluetooth no se emparejan](#bluetooth-devices-arent-pairing)
- [El micrófono USB-C no funciona](#usb-c-microphone-isnt-working)
- [Los dispositivos que aparecen como disponibles en Configuración no funcionan](#devices-listed-as-available-in-settings-dont-work)

## <a name="remote-assist-video-freezes-after-20-minutes"></a>Remote Assist vídeo se bloquea después de 20 minutos

> [!NOTE]
> Debido a la gravedad de este problema conocido, actualmente hemos pausado la disponibilidad de Windows Holographic, versión 21H1. Si desea seguir actualizando los dispositivos a 21H1, consulte las instrucciones de nuestras notas de la versión en la parte superior [de la página.](hololens-release-notes.md)

En la versión más reciente de [Windows Holographic, versión 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)algunos usuarios de Remote Assist han experimentado la inmovilización de vídeo durante las llamadas durante más de 20 minutos. Se trata de **un problema conocido.**

### <a name="workarounds"></a>Soluciones alternativas

#### <a name="restart-in-between-calls"></a>Reinicio entre llamadas

Si las llamadas tienen una duración de 20 minutos y está experimentando este problema, intente reiniciar el dispositivo. Reiniciar el dispositivo entre Remote Assist llamadas actualizará el dispositivo y lo volverá a poner en un buen estado.

Para reiniciar rápidamente un dispositivo en Windows Holographic, la versión [21H1](hololens-release-notes.md#windows-holographic-version-21h1) abre el menú Inicio y selecciona el icono de usuario y, a continuación, **selecciona Reiniciar**.

#### <a name="revert-to-an-older-build"></a>Revertir a una compilación anterior

Algunos clientes han descubierto que, al revertir a una versión anterior del sistema operativo, ya no experimentan este problema. Si ha descubierto que los dispositivos están experimentando este problema, pruebe estos pasos:


Soluciones alternativas:

- Si es viable para su empresa, la carga automática de la cámara se admite en las cuentas microsoft del consumidor. Puede iniciar sesión en su cuenta Microsoft además de la cuenta profesional o educativa (la aplicación OneDrive admite el inicio de sesión dual). Desde el perfil de la cuenta microsoft en OneDrive puede habilitar la carga automática de la cámara en segundo plano.

- Si no puede usar de forma segura una cuenta Microsoft de consumidor para cargar las fotos automáticamente, puede cargar manualmente las fotos en su cuenta laboral o educativa desde la aplicación OneDrive. Para ello, asegúrese de que ha iniciado sesión en su cuenta laboral o educativa en la aplicación OneDrive. Seleccione el **+** botón y elija **Cargar.** Para buscar las fotos o vídeos que desea cargar, vaya a **Imágenes > Camera Roll**. Seleccione las fotos o vídeos que desea cargar y, a continuación, seleccione el **botón** Abrir.


1. [Descarga de la compilación para Windows Holographic, versión 20H2: actualización de mayo de 2021](https://aka.ms/hololens2download/10.0.19041.1146)
1. Siga las [instrucciones para volver a una versión anterior del sistema operativo.](hololens-update-hololens.md#go-back-to-a-previous-version)
1. Pausar [las actualizaciones del sistema operativo en el dispositivo manualmente](hololens-updates.md#pause-updates-via-device) o, para muchos dispositivos, usar el [aplazamiento a través de MDM.](hololens-updates.md#configure-an-update-deferral-policy)

[Volver a la lista](#list)

## <a name="auto-login-asks-for-log-in"></a>Inicio de sesión automático pide inicio de sesión

Un HoloLens 2 se puede configurar para iniciar sesión automáticamente a través de Opciones de inicio de sesión de cuentas de configuración -> y en Obligatorio, estableciendo el valor  ->    ->   en **Nunca**.  Es posible que algunos usuarios deba iniciar sesión de nuevo en el dispositivo al actualizar un dispositivo con una actualización considerablemente grande, como una actualización de características. Se trata de **un problema conocido.**

Ejemplo de cuándo podría ocurrir:

- Actualización de un dispositivo desde Windows Holographic, versión 2004 (compilación 19041.xxxx) a Windows Holographic, versión 21H1 (compilación 20346.xxxx)
- Actualización de un dispositivo para realizar una actualización grande en la misma compilación principal, por ejemplo, Windows Holographic, versión 2004 a Windows Holographic, versión 20H2
- Actualización de un dispositivo de una imagen de fábrica a la imagen más reciente

Esto no debe ocurrir durante:

- Dispositivos que toman una actualización de mantenimiento mensual

Métodos de trabajo:

- Métodos de inicio de sesión como pin, contraseña, iris, autenticación web o claves FIDO2.
- Si no se puede recordar el PIN del dispositivo y no hay otros métodos de autenticación disponibles, un usuario puede usar el [modo de reflashación manual](hololens-recovery.md#manual-procedure).

[Volver a la lista](#list)

## <a name="microsoft-edge-fails-to-launch"></a>Microsoft Edge no se puede iniciar

> [!NOTE]
> Este problema se creó originalmente con la versión de envío Microsoft Edge en mente. Este problema se puede resolver en el [nuevo Microsoft Edge](hololens-new-edge.md). Si no es así, envíe sus comentarios.

Algunos clientes han notificado un problema por el Microsoft Edge no se puede iniciar. Para estos clientes, el problema persiste durante el reinicio y no se resuelve con las actualizaciones de Windows o de la aplicación. Si tiene este problema y ha confirmado que [Windows](hololens-updates.md#manually-check-for-updates)está actualizado, envíe un error desde la aplicación [Centro de opiniones](hololens-feedback.md) con la siguiente categoría y subcategoría: Instalación y actualización de > Descarga, instalación y configuración de Windows Update.

No hay soluciones alternativas conocidas, ya que hasta ahora no hemos podido resolver la causa principal del problema. La presentación de un error mediante Centro de opiniones ayudará a nuestra investigación. Se trata de **un problema conocido.**

[Volver a la lista](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a>El teclado no cambia a caracteres especiales

Hay un problema durante la OOBE, donde una vez que el usuario ha elegido una cuenta de trabajo o educativa y escribe su contraseña, intenta cambiar a los caracteres especiales del teclado pulsando el botón &123 no cambia a caracteres especiales. Se trata de **un problema conocido.**

Entornos de trabajo:
-   Cierre el teclado y vuelva a abrirlo pulsando en el campo de texto.
-   Escriba incorrectamente la contraseña. Cuando el teclado se vuelva a iniciar la próxima vez, funcionará según lo previsto.
- Autenticación web, cierre el teclado y seleccione **Iniciar sesión desde otro dispositivo.**
-   Si solo escribe números, un usuario puede presionar y mantener presionadas ciertas teclas para abrir un menú expandido.
-   Uso de un teclado USB.

Esto no afecta a:
- Usuarios que deciden usar una cuenta personal.

[Volver a la lista](#list)


## <a name="downloading-locked-files-doesnt-error"></a>No se produce un error al descargar archivos bloqueados
> ! NOTA Se trata de **un problema conocido** que se ha corregido en Windows Insider compilación, versión 20348.1403.


En compilaciones anteriores de Windows Holographic, al intentar descargar un archivo bloqueado, el resultado sería una página de error HTTP. En la actualización de Windows Holographic, versión 21H1, al intentar descargar un archivo bloqueado no ocurre nada visible: el archivo no se descarga y no hay ningún error. 

[Volver a la lista](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a>Portal de dispositivos de carga y descarga de archivos
> ! NOTA Se trata de **un problema conocido** que se ha corregido en Windows Insider compilación, versión 20348.1403. Si anteriormente deshabilitó la conexión SSL como parte de la solución alternativa, se recomienda encarecidamente volver a habilitarla.


Algunos clientes han descubierto que, al intentar cargar o descargar archivos, la operación puede parecer que se ha quedado y, a continuación, se ha completado el tiempo de espera o nunca se ha completado. Esto es independiente[](#downloading-locked-files-doesnt-error) del problema conocido de "archivo bloqueado", que afecta a las compilaciones en el mercado de Windows Holographic, versiones 2004, 20H2 y 21H1. El problema se ha originado en un error en el control de Portal de dispositivos de determinadas solicitudes y se produce de forma más coherente al usar https, que es el valor predeterminado. 

### <a name="workaround"></a>Solución alternativa

Esta solución alternativa, que se aplica igualmente a Wi-Fi y UsbNcm, consiste en deshabilitar la opción "obligatorio" en "Conexión SSL". Para ello, vaya a Portal de dispositivos, **Sistema** y seleccione la **página Preferencias.** En la **sección Seguridad del dispositivo,** busque **Conexión SSL** y desactive para deshabilitar **Requerido.**

A continuación, el usuario debe ir a http://, no https:// (dirección IP) y características como la carga y descarga de archivos funcionarán.

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
    - Flash en una compilación que no es interna. Una de las actualizaciones mensuales normales.
    - Permanecer en la versión preliminar de Insider
- Reflash the device (Volver a actualizar el dispositivo)

    1. Coloque el [HoloLens 2 en modo de](hololens-recovery.md) parpadeo manualmente al encender completamente sin conectarse. A continuación, mientras mantiene presionado Volumen, pulse el botón De encendido.
    
    1. Conéctese al equipo y abra Advanced Recovery Companion.
    
    1. Flash el HoloLens 2 a la compilación predeterminada.

[Volver a la lista](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a>OneDrive no carga automáticamente imágenes

La aplicación OneDrive para HoloLens no admite la carga automática de cámaras para cuentas profesionales o educativas. Se trata de **un problema conocido.**

Soluciones alternativas:

- Si es viable para su empresa, la carga automática de la cámara se admite en las cuentas microsoft del consumidor. Puede iniciar sesión en su cuenta Microsoft además de la cuenta profesional o educativa (la aplicación OneDrive admite el inicio de sesión dual). Desde el perfil de la cuenta microsoft en OneDrive puede habilitar la carga automática de la cámara en segundo plano.

- Si no puede usar de forma segura una cuenta Microsoft de consumidor para cargar las fotos automáticamente, puede cargar manualmente las fotos en su cuenta laboral o educativa desde la aplicación OneDrive. Para ello, asegúrese de que ha iniciado sesión en su cuenta laboral o educativa en la aplicación OneDrive. Seleccione el **+** botón y elija **Cargar.** Para buscar las fotos o vídeos que desea cargar, vaya a **Imágenes > Camera Roll**. Seleccione las fotos o vídeos que desea cargar y, a continuación, seleccione el **botón** Abrir.

[Volver a la lista](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a>HoloLens no responde o no se inicia

Si holoLens no se inicia:

- Si los LED situados junto al botón de encendido no se encienden o solo un LED parpadea brevemente, es posible que deba cargar [holoLens.](hololens2-charging.md#charging-the-device)
- Si los LED se encienden al presionar el botón de encendido, pero no puede ver nada en las pantallas, realice un restablecimiento de forma fuerte [del dispositivo.](hololens-recovery.md#hard-reset-procedure)

Si HoloLens se inmoviliza o deja de responder:

- Desactive HoloLens presionando el botón de encendido hasta que los cinco LED se apaguen o durante 15 segundos si los LED no responden. Para iniciar HoloLens, vuelva a presionar el botón de encendido.

Si estos pasos no funcionan, puede intentar recuperar el dispositivo [HoloLens 2](hololens-recovery.md) o [dispositivo HoloLens (1.ª generación).](hololens1-recovery.md)

[Volver a la lista](#list)

## <a name="low-disk-space-error"></a>Error "Espacio en disco bajo"

Tendrá que liberar espacio de almacenamiento realizando una o varias de las siguientes acciones:

- Elimine algunos espacios no usados. Vaya a **Configuración** Espacios del sistema, seleccione un espacio que ya no necesite  >    >  y, a continuación, **seleccione Quitar**.
- Quite algunos de los hologramas que ha colocado.
- Elimine algunas imágenes y vídeos de la aplicación Fotos.
- Desinstale algunas aplicaciones de HoloLens. En la **lista Todas las** aplicaciones, mantenga presionada la aplicación que desea desinstalar y, a continuación, seleccione **Desinstalar**.

[Volver a la lista](#list)

## <a name="calibration-fails"></a>Error de calibración

La calibración debería funcionar para la mayoría de las personas, pero hay casos en los que se produce un error en la calibración.
  
Entre los posibles motivos del error de calibración se incluyen:

- Distraerse y no seguir los objetivos de calibración
- Visor de dispositivos o visores de dispositivos desnuciados o rascados que no están correctamente posicionados
- Gafas desnuciadas o rayadas
- Ciertos tipos de lentes de contacto y gafas (lentes de contacto coloreadas, algunas lentes de contacto toréricas, gafas de bloqueo de IR, gafas de sol de alta graduación, gafas de sol o similares)
- Una composición más pronunciada y algunas extensiones de pestañas
- Marcos de gafas gruesas o de vello si impiden que el dispositivo vea los ojos
- Cierta fisonología ocular, condiciones oculares o cáncer de ojo, como ojos estrechos, pestañas largas, amblyopia, nistagmus, algunos casos de LASIK u otras operaciones oculares

Si la calibración no se realiza correctamente, pruebe:

- Limpieza del visor del dispositivo
- Limpieza de las gafas
- Insertar el visor del dispositivo lo más cerca posible de los ojos
- Mover objetos del visor fuera del camino (por ejemplo, el vello)
- Encender una luz en la habitación o salir de la luz directa

Si ha seguido todas las directrices y la calibración sigue teniendo errores, puede deshabilitar el símbolo del sistema de calibración en Configuración. Háganoslo saber también mediante la presentación de comentarios [en Centro de opiniones](hololens-feedback.md).

Consulte también la información relacionada para la [solución de problemas de color de imagen o brillo.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)

La configuración de IPD no es aplicable HoloLens 2, ya que el sistema calcula las posiciones de los ojos. 

[Volver a la lista](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a>No se puede iniciar sesión porque holoLens se ha configurado previamente para otra persona.

Puede poner [el dispositivo en modo de **flashing y** usar Advanced Recovery Companion](hololens-recovery.md#clean-reflash-the-device) para recuperar el dispositivo.

[Volver a la lista](#list)


## <a name="unity-isnt-working"></a>Unity no funciona

- Consulte [Instalación de las herramientas](/windows/mixed-reality/install-the-tools) para obtener la versión más actualizada de Unity recomendada para el desarrollo de HoloLens.
- Los problemas conocidos de Unity HoloLens Technical Preview se documentan en los [foros de Unity de HoloLens.](https://forum.unity3d.com/threads/known-issues.394627/)

[Volver a la lista](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a>Portal de dispositivos Windows no funciona correctamente

- La característica Live Preview de Mixed Reality captura puede presentar varios segundos de latencia.

- En la página Entrada virtual, los controles Gesto y Desplazamiento de la sección Gestos virtuales no son funcionales. Su uso no tendrá ningún efecto. El teclado virtual de la página de entrada virtual funciona correctamente.

- Después de habilitar el modo de desarrollador en Configuración, puede tardar unos segundos antes de que el conmutador active el Portal de dispositivos está habilitado.

[Volver a la lista](#list)

## <a name="emulator"></a>Emulador
### <a name="the-hololens-emulator-isnt-working"></a>El emulador de HoloLens no funciona

La información sobre el emulador de HoloLens se encuentra en nuestra documentación para desarrolladores.  Obtenga más información sobre [cómo solucionar problemas del emulador de HoloLens.](/windows/mixed-reality/using-the-hololens-emulator#troubleshooting)


- No todas las aplicaciones del Microsoft Store son compatibles con el emulador. Por ejemplo, Young Conker y Fragments no se pueden reproducir en el emulador.
- No puede usar la cámara web del equipo en el emulador.
- La característica Live Preview del Portal de dispositivos Windows no funciona con el emulador. Todavía puede capturar vídeos Mixed Reality imágenes.

[Volver a la lista](#list)

## <a name="i-cannot-find-or-use-the-keyboard-to-type-in-the-hololens-2-emulator"></a>No puedo encontrar ni usar el teclado para escribir en el emulador de HoloLens 2.

*Próximamente*

[Volver a la lista](#list)

## <a name="voice-commands-arent-working"></a>Los comandos de voz no funcionan

Si Cortana no responde a los comandos de voz, asegúrese de que Cortana está activado. En la lista Todas las aplicaciones, seleccione **Configuración del** cuaderno de  >  **menús** de Cortana  >    >   para realizar cambios. Para más información sobre lo que puede decir, consulte [Uso de la voz con HoloLens.](hololens-cortana.md)

En HoloLens (1ª generación), el reconocimiento de voz integrado no es configurable. Siempre está activado. En HoloLens 2, puede elegir si quiere activar el reconocimiento de voz y Cortana durante la configuración del dispositivo.

Si el HoloLens 2 no responde a su voz, asegúrese de que el reconocimiento de voz está activado. Vaya a **Configuración de inicio**  >  **Privacidad**  >    >  **Voz** y active Reconocimiento **de voz.**

[Volver a la lista](#list)

## <a name="hand-input-isnt-working"></a>La entrada de mano no funciona

Para asegurarse de que HoloLens puede ver las manos, debe mantenerlas en el marco de gestos.  El Mixed Reality Home proporciona comentarios que le permiten saber cuándo se realiza el seguimiento de las manos.  Los comentarios son diferentes en las distintas versiones de HoloLens:
- En HoloLens (1ª generación), el cursor de mirada cambia de un punto a un anillo.
- En HoloLens 2, aparece un cursor de dedo cuando la mano está cerca de una pizarra y aparece un rayo cuando las pizarras están más alejadas

Muchas aplicaciones envolventes siguen patrones de entrada similares a Mixed Reality Inicio.  Obtenga más información sobre el uso de la entrada a mano [en HoloLens (1ª generación)](hololens1-basic-usage.md#use-hololens-with-your-hands) [y HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).

Si va a llevar unas gafas, tenga en cuenta que algunos tipos de camisetas no funcionan con el seguimiento de las manos.  Un ejemplo común es el de la caja negra, que tiende a absorber la luz de los rejas y no la toma la cámara de profundidad.  Si el trabajo implica una insondación de ruedas, se recomienda probar un color más claro, como azul o gris.  Otro ejemplo es una bolsa grande, que tiende a ocultar la forma de la mano. Se recomienda usar un procedimiento que sea lo más apropiado posible para obtener los mejores resultados.

Si el visor tiene huellas digitales o marcas, use la limpieza de microfibras que se incluye con HoloLens para limpiar el visor de forma natural.

[Volver a la lista](#list)

## <a name="cant-connect-to-wi-fi"></a>No se puede conectar a Wi-Fi

Estos son algunos aspectos que se pueden probar si no se puede conectar HoloLens a una Wi-Fi virtual:

- Asegúrese de que Wi-Fi está activado. Para comprobarlo, use el gesto Iniciar y, a continuación, seleccione **Configuración**  >  **&amp; Red**  >  **Wi-Fi de Internet.** Si Wi-Fi está encendido, intente desactivarlo y, a continuación, vuelva a activarlo.
- Acercarse al enrutador o al punto de acceso.
- Reinicie el enrutador Wi-Fi y, a [continuación, reinicie HoloLens.](hololens-recovery.md) Try connecting again (Intente conectarse de nuevo).
- Si ninguna de estas cosas funciona, asegúrese de que el enrutador usa el firmware más reciente. Puede encontrar esta información en el sitio web del fabricante.

[Volver a la lista](#list)
## <a name="bluetooth-devices-arent-pairing"></a>Los dispositivos Bluetooth no se emparejan

Si tiene problemas para [emparejar un dispositivo Bluetooth,](hololens-connect-devices.md)pruebe lo siguiente:

- Vaya a **Configuración**  >  **Dispositivos** y asegúrese de que Bluetooth está activado. Si es así, descándalo y vuelva a activarlo.
- Asegúrese de que el dispositivo Bluetooth está totalmente cargado o tiene baterías nuevas.
- Si aún no puede conectarse, [reinicie HoloLens.](hololens-recovery.md)

[Volver a la lista](#list)

## <a name="usb-c-microphone-isnt-working"></a>El micrófono USB-C no funciona
Tenga en cuenta que algunos micrófonos USB-C se informan incorrectamente como micrófono *y* altavoz. Se trata de un problema con el micrófono y no con HoloLens. Al conectar uno de estos micrófonos a HoloLens, es posible que se pierda el sonido. Afortunadamente, hay una corrección sencilla.  

En **Configuración** de sonido del sistema , establezca explícitamente los altavoces integrados (controlador de audio de características  ->    ->   **análogas)** como **el dispositivo predeterminado**. HoloLens debe recordar esta configuración incluso si el micrófono se quita y se vuelve a conectar más adelante.

![Solución de problemas de micrófonos USB-C](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a>Los dispositivos que aparecen como disponibles en Configuración no funcionan

HoloLens (1.ª generación) no admite perfiles de audio Bluetooth. Los dispositivos de audio Bluetooth, como altavoces y cascos, pueden aparecer como disponibles en la configuración de HoloLens, pero no se admiten.

HoloLens 2 admite el perfil de audio Bluetooth A2DP para la reproducción estéreo. El perfil Bluetooth Hands Free que permite la captura de micrófono desde un periférico Bluetooth no se admite en HoloLens 2.

Si tiene problemas para usar un dispositivo Bluetooth, asegúrese de que es un dispositivo compatible. Entre los dispositivos admitidos se incluyen los siguientes:

- Teclados Bluetooth QWERTY en inglés (puede usarlos en cualquier lugar en el que use el teclado holográfico).
- Bluetooth mouse.
- El [botón de clic de HoloLens.](hololens1-clicker.md)

Puede emparejar otros dispositivos Bluetooth HID y NFC junto con holoLens. Sin embargo, es posible que tenga que instalar las aplicaciones complementarias correspondientes Microsoft Store usar realmente los dispositivos.

[Volver a la lista](#list)
