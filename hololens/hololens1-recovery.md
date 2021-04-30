---
title: Reinicio, restablecimiento o recuperación de HoloLens 1
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: Cómo usar la herramienta de recuperación de dispositivos Windows para flashear una imagen en HoloLens 1.ª generación.
keywords: how-to, reboot, reset, recover, hard reset, soft reset, power cycle, HoloLens, shut down, wdrt, windows device recovery tool
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.date: 06/01/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: medium
manager: yannisle
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: f50a885f6cc82256d146d7f4914aca934e81c0c0
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2021
ms.locfileid: "108310136"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a>Reinicio, restablecimiento o recuperación de HoloLens (1.ª generación)

Si tiene problemas con HoloLens, puede que quiera probar un reinicio o restablecimiento, o incluso volver a actualizar el dispositivo mediante la recuperación de dispositivos. Este artículo le guía por los pasos de recuperación recomendados en orden.

Si desea recuperar un HoloLens 2, consulte [Recuperación](https://docs.microsoft.com/hololens/hololens-recovery)de un HoloLens 2 , ya que ese proceso difiere.

> [!NOTE]
> Este artículo se centra en el dispositivo y el software de HoloLens. Si los hologramas no son **[correctos,](hololens-environment-considerations.md)** consulte Consideraciones del entorno de HoloLens para obtener información sobre los factores que mejoran la calidad del holograma.

## <a name="restart"></a>Reiniciar

### <a name="do-a-safe-restart-by-using-cortana"></a>Realizar un reinicio seguro mediante Cortana

La manera más segura de reiniciar HoloLens es mediante Cortana, que suele ser lo primero que hay que probar cuando se experimenta un problema con HoloLens.

> [!NOTE] 
> Cortana no está disponible en todos los dispositivos.
> - Cortana está disponible en todos los dispositivos HoloLens (1.ª generación). 
> - Cortana está disponible en HoloLens 2 en compilaciones anteriores a la actualización de Windows Holograpic, versión 2004.

1. Active HoloLens.
1. Asegúrese de que un usuario ha iniciado sesión y que el dispositivo no espera a que una contraseña la desbloquee.
2. Diga "Hola Cortana, reinicie" o "Hola Cortana, reinicie".
3. Cortana responderá y le pedirá que lo confirme. Espere a que se reprodgue un sonido después de la pregunta y, a continuación, diga "Sí". El dispositivo se reiniciará.

### <a name="use-the-power-button-to-do-a-safe-restart"></a>Uso del botón de encendido para realizar un reinicio seguro

Si todavía no puede reiniciar el dispositivo, intente reiniciarlo con el **botón de** encendido:

1. Mantenga presionado el **botón de** encendido durante 5 segundos. Después de 1 segundo, los cinco LED se encienden y, a continuación, se apagan lentamente uno por uno de derecha a izquierda. Después de 5 segundos, todos los LED estarán apagados, lo que indica un apagado correcto.
      
   > [!IMPORTANT]
   > Deje de presionar el botón inmediatamente después de que se apaguen todos los LED.
1. Espere 1 minuto a que se complete el apagado. El apagado puede seguir en curso incluso después de que se apaguen las pantallas.
2. Vuelva a encender el dispositivo presionando y manteniendo presionado **el botón de** encendido durante 1 segundo.

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a>Realice un reinicio seguro mediante Portal de dispositivos Windows

> [!NOTE]
> Para este proceso, HoloLens debe configurarse como un dispositivo para desarrolladores. Obtenga más información [en Portal de dispositivos Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).

Si el procedimiento anterior no funcionaba, intente reiniciar el dispositivo mediante [Portal de dispositivos Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal). En la esquina superior derecha, busque la opción para reiniciar o apagar el dispositivo.

### <a name="do-an-unsafe-forced-restart"></a>Realizar un reinicio forzado no seguro

Si los métodos anteriores no reiniciaron HoloLens, fuerce un reinicio. Este método equivale a quitar y volver a instalar la batería. Es peligroso porque podría dejar el dispositivo en estado dañado. Si esto sucede, tendrá que flashear HoloLens.  

> [!WARNING]
> Se trata de un método potencialmente perjudicial y solo se debe usar si los métodos mencionados anteriormente no funcionaban.

1. Mantenga presionado el **botón de** encendido durante al menos 10 segundos.
   - Es correcto mantener presionado el botón durante más de 10 segundos.
   - Es seguro omitir cualquier actividad DE LED.
1. Suelte el botón y espere entre 2 y 3 segundos.
1. Mantenga presionado el **botón de** encendido durante 1 segundo.
1. Si sigue teniendo problemas,  presione el botón de encendido durante 4 segundos, hasta que todos los indicadores de batería se apaguen y la pantalla deje de mostrar hologramas. Espere 1 minuto y, a continuación, vuelva **a presionar el botón de** encendido para activar el dispositivo.

## <a name="reset-to-factory-settings"></a>Restablecimiento de la configuración de fábrica

> [!NOTE]
> La batería necesita al menos un 40 por ciento de carga para restablecerse.

Si holoLens sigue teniendo un problema, intente restablecerlo al estado de fábrica. Este paso mantiene la versión del software de Windows Holographic que está instalado en él y devuelve todo lo demás a la configuración de fábrica.

>[!WARNING]
> Si restablece el dispositivo, se borrarán todos los datos personales, las aplicaciones y la configuración, incluida la información de restablecimiento de TPM. El restablecimiento solo instalará la versión instalada más reciente de Windows Holographic. Tendrá que rehacer todos los pasos de inicialización (calibrar, conectarse a Wi-Fi, crear una cuenta de usuario, descargar aplicaciones, entre otros).

1. Abra la aplicación Configuración y, a continuación, **seleccione Actualizar**  >  **recuperación.**
1. Seleccione la opción **Restablecer dispositivo** y lea el mensaje de confirmación.
1. Confirme el restablecimiento. El dispositivo se reiniciará y mostrará un conjunto de engranajes giratorios y una barra de progreso.
1. Espere unos 30 minutos a que se complete este proceso. Cuando haya terminado, el dispositivo se reiniciará en la experiencia "lista para su uso".

## <a name="reinstall-the-operating-system"></a>Reinstalación del sistema operativo

Si el dispositivo sigue teniendo un problema después del reinicio y el restablecimiento, puede usar una herramienta de recuperación en el equipo para volver a instalar el firmware y el sistema operativo HoloLens.  

Los datos que HoloLens necesita para el restablecimiento se empaquetan en una actualización flash completa (FFU), que es similar a un archivo .iso, .wim o .vhd. [Obtenga información sobre los formatos de archivo de imagen de FFU.](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

Puede instalar un nuevo sistema operativo en HoloLens (1ª generación) mediante la herramienta de recuperación de dispositivos de Windows. Antes de usar esa herramienta, vea si el reinicio o el restablecimiento de HoloLens corrige el problema.

El proceso de recuperación puede tardar un tiempo. Cuando haya terminado, se instalará la versión más reciente del software Windows Holographic.

Para usar la herramienta, necesita un equipo que ejecute Windows 10 o posterior con al menos 4 GB de espacio de almacenamiento libre. No se puede ejecutar esta herramienta en una máquina virtual.

### <a name="recover-your-hololens"></a>Recuperación de HoloLens

1. Descargue e instale la Herramienta [de recuperación de dispositivos Windows](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) en el equipo.
1. Conecte HoloLens (1.ª generación) al equipo mediante el cable Micro USB que se incluye con HoloLens.
1. Abra la Herramienta de recuperación de dispositivos Windows y siga las instrucciones.

Si HoloLens (1ª generación) no se detecta automáticamente, seleccione **Mi dispositivo no se detectó.** A continuación, siga las instrucciones para poner el dispositivo en modo de recuperación.

### <a name="manual-flashing-mode"></a>Modo de parpadeo manual

Si no se detecta el dispositivo, siga estos pasos para ponerlo en modo de parpadeo:

1. Desconecte el dispositivo de cualquier fuente de alimentación.
1. Si el dispositivo está encendido, mantenga presionado el **botón de** encendido hasta que se apague completamente.
2. Mantenga presionado **el botón de** volumen y pulse brevemente el botón **de** encendido. El dispositivo debe iniciarse y mostrar solo la luz LED central.
3. Conecte el dispositivo al equipo.
4. Abra la Herramienta de recuperación de dispositivos Windows.
5. Seleccione **Mi dispositivo no se detectó y,** a **continuación, HoloLens.** 
6. Siga las instrucciones para recuperar el dispositivo.
